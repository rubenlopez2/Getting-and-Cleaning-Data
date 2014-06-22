To work the script must be in the same directory as the "UCI HAR Dataset" file. Throught the script, unused data is cleared out.

The first thing the script does is read the activity labels and save them as activity_labels. Then it reads the set, test, and subject files for both the Test values and Training values and saves them separately.

It creates a "test" and a "training" set by just using cbind to put the subject and labels toguether, then it gives it column lables.

The script then creates two data frames. One with all the subject/labels as "super" and one with all the sensor data called "data". 
The next thing it does is download the feature file, which has the names for each of the readings. To find the mean() and the std() (mean and standard deviation as defined, the angular mean values are derivative and were not included), it uses two for loops. These use the grepl function to find the mean() and std() strings. Then it creates a logical vector for each loop to identify where they exist. Then it creates a master logical vector with an OR statement. Afterwards it extracts those values by creating a subset with the logical vector named "data_clean" and then labeling that data set.

Afterwards it runs another for loop to exchange the activity #s with the activity names by stripping the activity vector from the "activity_labels" and using the positions to create another vector. Then this vector is replaced into the "super" data frame. 

For the next part, the reshape2 library is loaded in order to use the dcast function. the subject/activity data frame is combined with the "data_clean" subset to create  the "complete" data frame. The dcast function is used (after suppressing warnings) to create unique subject/activity instances and the sensor mean and standard deviation values are averaged. This is saved as "tidy_data". Then this dataframe is exported as a tab-delimited text file by using the write.table function.
