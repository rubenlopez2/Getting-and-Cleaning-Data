#Script must be in the same directory as the "UCI HAR Dataset" file

# Read the activity labels
activity_labels <- read.table("./UCI HAR Dataset/activity_labels.txt", quote="\"")

#Read the Test values
test_set <- read.table("./UCI HAR Dataset/test/X_test.txt", quote="\"", stringsAsFactors=FALSE)
test_labels <- read.table("./UCI HAR Dataset/test/y_test.txt", quote="\"")
test_subject <- read.table("./UCI HAR Dataset/test/subject_test.txt", quote="\"")

#Read the Training values
training_set <- read.table("./UCI HAR Dataset/train/X_train.txt", quote="\"", stringsAsFactors=FALSE)
training_labels <- read.table("./UCI HAR Dataset/train/y_train.txt", quote="\"")
training_subject <- read.table("./UCI HAR Dataset/train/subject_train.txt", quote="\"")

#Create test set
test <- cbind(test_subject,test_labels)

#Clean out the enviroment
rm(test_subject,test_labels)
#Label the test set
colnames(test)[1] <- "subject"
colnames(test)[2] <- "activity"

#Create training set
training <- cbind(training_subject,training_labels)
#Clean out the enviroment
rm(training_subject,training_labels)
colnames(training)[1] <- "subject"
colnames(training)[2] <- "activity"

#Merge data frames, super has the test instance and activity data, data has all the data
super <- merge(test,training, all=TRUE)
data <- merge(test_set,training_set, all=TRUE)
#Clean out the enviroment
rm(test,training,test_set,training_set)

#Download features, this checks for the mean and std in the strings and creates a logical
#vector for each to identify which data columns have mean or std values
features <- read.table("./UCI HAR Dataset/features.txt", quote="\"")
row_features <- nrow(features)

features_test1 <- NULL
for(i in 1:row_features){
  val <- grepl("mean()",features[i,2])
  features_test1 <- c(features_test1,val)
}

features_test2 <- NULL
for(i in 1:row_features){
  val <- grepl("std()",features[i,2])
  features_test2 <- c(features_test2,val)
}
#Creates a comprehensive logical value by using OR
feature_test <- features_test1 | features_test2
rm(i,val,row_features,features_test1,features_test2)
feature_names <- features[feature_test,2]

#Extract mean() and sd() values from the data set
data_clean <- data[,feature_test]
colnames(data_clean) <- feature_names

#Label the activities with names
row_super <- nrow(super)
activity <- NULL
activity_1 <- as.vector(activity_labels$V2)
for(i in 1:row_super){
  x <- as.numeric(super[i,2])
  current_activity <- activity_1[x]
  activity <- c(activity,current_activity)
}

super[,2] <- activity
#Clean the enviroment
rm(data,features,activity_labels,x,i,current_activity,activity_1,row_super,feature_test)

#Load the reshape2 library in order to use the dcast function
library(reshape2)

#Creates a data frame with all the observations
complete <-cbind(super,data_clean)
#Clean the enviroment
rm(super,data_clean)
#Suppress warnings
options(warn = -1)
#Uses dcast to get unique subject/activy rows and takes the mean of all the non-na values within the
#mean and std columns
tidy_data <- dcast(complete, subject + activity ~ feature_names, fun.aggregate = mean, na.rm = TRUE)
#Enables warnings
options(warn = 0)
#Clean the enviroment
rm(feature_names,activity)
#Outputs the tidy.tx file to the source directory
write.table(tidy_data,"./tidy.txt", sep="\t",row.names=F)
