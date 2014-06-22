

Files used in order:

1.  activity_labels.txt   Links the class labels with their activity name.
2.  X_test.txt    Test set.
3.  y_test.txt    Test labels.
4.  subject_test.txt  List of the subject used in the test.
5.  X_train.txt   Training sets
6.  y_train.txt   Training labels.
7.  subject_train.txt   List of the subject used in the training.
8.  features.txt  List of all features.
9.  feature_info.txt    Used to get all the information about what the features means for the Data Dictionary.

Output file:

tidy.txt    Tab delimeted tidy data set. It has 81 columns (definitions below) and 180 rows for each of the possible combinations of subject x activity (30 x 6 = 180). Combinations for where there is no information have NA values.

Data Dictionary

Each colum

1.    Subject   1-30 to identify the subjects that wore the sensors to gather the data.
2.    Activity    One of the following 6 activities that the subjects were involved with
      - WALKING
      - WALKING_UPSTAIRS
      - WALKING_DOWNSTAIRS
      - SITTING
      - STANDING
      - LAYING

For the other mean and standard deviation the mean/average value of all observations within a subject/activity combination is displayed. The X-Y-Z values for mean() and std() are displayed as separate columns. The angle Mean values are not included.

All other variables denote the mean of all the observable data for mean and standard deviation with NA value ignored in the calculations.

The data from accelerometer and gyroscope 3-axial raw signals is denoted as tAcc and tGyro with the respective X-Y-Z values. The t-prefix is used for time (captured at 50Hz) and the the f-prefix is used to indicate the frequency (using a Fast Fourier Transform). The Gravity signal is derived withing a Butterworth filter (corner frequency of .3Hz). The angular velocity is derived in time to obtain a Jerk signal.

** ALL CREDIT FOR THE MEANING OF THE VARIABLES COMES FROM THE ORIGINAL AUTHORS (see features_info.txt).
1.    Subject placeholder -- ignore
2.    Activity placeholder -- ignore
3.	tBodyAcc-mean()-X
4.	tBodyAcc-mean()-Y
5.	tBodyAcc-mean()-Z
6.	tBodyAcc-std()-X
7.	tBodyAcc-std()-Y
8.	tBodyAcc-std()-Z
9.	tGravityAcc-mean()-X
10.	tGravityAcc-mean()-Y
11.	tGravityAcc-mean()-Z
12.	tGravityAcc-std()-X
13.	tGravityAcc-std()-Y
14.	tGravityAcc-std()-Z
15.	tBodyAccJerk-mean()-X
16.	tBodyAccJerk-mean()-Y
17.	tBodyAccJerk-mean()-Z
18.	tBodyAccJerk-std()-X
19.	tBodyAccJerk-std()-Y
20.	tBodyAccJerk-std()-Z
21.	tBodyGyro-mean()-X
22.	tBodyGyro-mean()-Y
23.	tBodyGyro-mean()-Z
24.	tBodyGyro-std()-X
25.	tBodyGyro-std()-Y
26.	tBodyGyro-std()-Z
27.	tBodyGyroJerk-mean()-X
28.	tBodyGyroJerk-mean()-Y
29.	tBodyGyroJerk-mean()-Z
30.	tBodyGyroJerk-std()-X
31.	tBodyGyroJerk-std()-Y
32.	tBodyGyroJerk-std()-Z
33.	tBodyAccMag-mean()
34.	tBodyAccMag-std()
35.	tGravityAccMag-mean()
36.	tGravityAccMag-std()
37.	tBodyAccJerkMag-mean()
38.	tBodyAccJerkMag-std()
39.	tBodyGyroMag-mean()
40.	tBodyGyroMag-std()
41.	tBodyGyroJerkMag-mean()
42.	tBodyGyroJerkMag-std()
43.	fBodyAcc-mean()-X
44.	fBodyAcc-mean()-Y
45.	fBodyAcc-mean()-Z
46.	fBodyAcc-std()-X
47.	fBodyAcc-std()-Y
48.	fBodyAcc-std()-Z
49.	fBodyAcc-meanFreq()-X
50.	fBodyAcc-meanFreq()-Y
51.	fBodyAcc-meanFreq()-Z
52.	fBodyAccJerk-mean()-X
53.	fBodyAccJerk-mean()-Y
54.	fBodyAccJerk-mean()-Z
55.	fBodyAccJerk-std()-X
56.	fBodyAccJerk-std()-Y
57.	fBodyAccJerk-std()-Z
58.	fBodyAccJerk-meanFreq()-X
59.	fBodyAccJerk-meanFreq()-Y
60.	fBodyAccJerk-meanFreq()-Z
61.	fBodyGyro-mean()-X
62.	fBodyGyro-mean()-Y
63.	fBodyGyro-mean()-Z
64.	fBodyGyro-std()-X
65.	fBodyGyro-std()-Y
66.	fBodyGyro-std()-Z
67.	fBodyGyro-meanFreq()-X
68.	fBodyGyro-meanFreq()-Y
69.	fBodyGyro-meanFreq()-Z
70.	fBodyAccMag-mean()
71.	fBodyAccMag-std()
72.	fBodyAccMag-meanFreq()
73.	fBodyBodyAccJerkMag-mean()
74.	fBodyBodyAccJerkMag-std()
75.	fBodyBodyAccJerkMag-meanFreq()
76.	fBodyBodyGyroMag-mean()
77.	fBodyBodyGyroMag-std()
78.	fBodyBodyGyroMag-meanFreq()
79.	fBodyBodyGyroJerkMag-mean()
80.	fBodyBodyGyroJerkMag-std()
81.	fBodyBodyGyroJerkMag-meanFreq()

All values are mean observation values for mean() and std().

** ALL CREDIT FOR THE MEANING OF THE VARIABLES COMES FROM THE ORIGINAL AUTHORS (see features_info.txt).

