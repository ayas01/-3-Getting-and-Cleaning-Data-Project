# Project Data's Code Book
### Ayas Shaqour

## Intoduction 
This is a Code Book describing the Data and Variables included in the Getting and cleaning data Course Project. 

## Source Data
The source data (raw data) for this project was obtianed from the **_UCL Machine Learning_** Repository called: **_Human Activity Recognition Using Smartphones Data Set_**. 

The link to their **Website** can be found [here](http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones)

The **Data** link can be found [here](http://archive.ics.uci.edu/ml/machine-learning-databases/00240/UCI%20HAR%20Dataset.zip)

The **Original data discription** can be found [here](http://archive.ics.uci.edu/ml/machine-learningdatabases/00240/UCI%20HAR%20Dataset.names)

## Tidy Data
The final dataset for this project consists of 1 file - “tidydata.txt”

The Dimension of the final data set is: 180 rows, 81 columns 

### Description 

Each row represents each subject (1-30) and each activity per subject, (6) activites.

The columns are the mean of each selected feature; the selected features are the ones that contained mean and standard deviation measurements from the original features.

### First two columns 
-Subject : The Id of the subjects (1-30)
-Activity: The type of movement they had
  -WALKING
  -WALKING_UPSTAIRS
  -WALKING_DOWNSTAIRS
  -SITTING
  -STANDING
  -LAYING
 ### The rest of the columns (Means of the selected features)

-Mean Of Time Body Accelerometer Mean X
-Mean Of Time Body Accelerometer Mean Y
-Mean Of Time BodyAccelerometer MeanZ
-Mean Of Time Body Accelerometer Std X
-Mean Of Time Body Accelerometer Std Y
-Mean Of Time Body Accelerometer Std Z
-Mean Of Time Gravity Accelerometer Mean X
-Mean Of Time Gravity Accelerometer Mean Y
-Mean Of Time Gravity Accelerometer Mean Z
-Mean Of Time Gravity Accelerometer Std X
-Mean Of Time Gravity Accelerometer Std Y
-Mean Of Time Gravity Accelerometer Std Z
-Mean Of Time Body Accelerometer Jerk Mean X
-Mean Of Time Body Accelerometer Jerk Mean Y 
-Mean Of Time Body Accelerometer Jerk Mean Z
-Mean Of Time Body Accelerometer Jerk Std X
-Mean Of Time Body Accelerometer Jerk Std Y
-Mean Of Time Body Accelerometer Jerk Std Z
-Mean Of Time Body Gyroscope Mean X
-Mean Of Time Body Gyroscope Mean Y
-Mean Of Time Body Gyroscope Mean Z
-Mean Of Time Body Gyroscope Std X 
-Mean Of Time Body Gyroscope Std Y
-Mean Of Time Body Gyroscope Std Z
-Mean Of Time Body Gyroscope Jerk Mean X
-Mean Of Time Body Gyroscope Jerk Mean Y
-Mean Of Time Body Gyroscope Jerk Mean Z
-Mean Of Time Body Gyroscope Jerk Std X
-Mean Of Time Body Gyroscope Jerk Std Y
-Mean Of Time Body Gyroscope Jerk Std Z
-Mean Of Time Body Accelerometer Magnitude Mean
-Mean Of Time Body Accelerometer Magnitude Std
-Mean Of Time Gravity Accelerometer Magnitude Mean
-Mean Of Time Gravity Accelerometer Magnitude Std
-Mean Of Time Body Accelerometer Jerk Magnitude Mean
-Mean Of Time Body Accelerometer Magnitude Std
-Mean Of Time Body Gyroscope Magnitude Mean
-Mean Of Frequency Body Gyroscope Magnitude Std
-Mean Of Time Body Gyroscope Jerk Magnitude Mean
-Mean Of Frequency Body Gyroscope JerkMagnitude Std
-Mean Of Frequency Body Accelerometer Mean X
-Mean Of Frequency Body Accelerometer Mean Y
-Mean Of Frequency Body Accelerometer Mean Z
-Mean Of Frequency Body Accelerometer Std X
-Mean Of Frequency Body Accelerometer Std Y
-Mean Of Frequency Body Accelerometer Std Z
-Mean Of (fBodyAcc-meanFreq()-X)"
-Mean Of (fBodyAcc-meanFreq()-Y)"
-Mean Of (fBodyAcc-meanFreq()-Z)"
-Mean Of (fBodyAccJerk-mean()-X)"
-Mean Of (fBodyAccJerk-mean()-Y)"
-Mean Of (fBodyAccJerk-mean()-Z)"
-Mean Of (fBodyAccJerk-std()-X)"
-Mean Of (fBodyAccJerk-std()-Y)"
-Mean Of (fBodyAccJerk-std()-Z)"
-Mean Of (fBodyAccJerk-meanFreq()-X)"
-Mean Of (fBodyAccJerk-meanFreq()-Y)"
-Mean Of (fBodyAccJerk-meanFreq()-Z)"
-Mean Of (fBodyGyro-mean()-X)"
-Mean Of (fBodyGyro-mean()-Y)"
-Mean Of (fBodyGyro-mean()-Z)"
-Mean Of (fBodyGyro-std()-X)"
-Mean Of (fBodyGyro-std()-Y)"
-Mean Of (fBodyGyro-std()-Z)"
-Mean Of (fBodyGyro-meanFreq()-X)"
-Mean Of (fBodyGyro-meanFreq()-Y)"
-Mean Of (fBodyGyro-meanFreq()-Z)"
-Mean Of (fBodyAccMag-mean())"
-Mean Of (fBodyAccMag-std())"
-Mean Of (fBodyAccMag-meanFreq())"
-Mean Of (fBodyBodyAccJerkMag-mean())"
-Mean Of (fBodyBodyAccJerkMag-std())"
-Mean Of (fBodyBodyAccJerkMag-meanFreq())"
-Mean Of (fBodyBodyGyroMag-mean())"
-Mean Of (fBodyBodyGyroMag-std())"
-Mean Of (fBodyBodyGyroMag-meanFreq())"
-Mean Of (fBodyBodyGyroJerkMag-mean())"
-Mean Of (fBodyBodyGyroJerkMag-std())"
-Mean Of (fBodyBodyGyroJerkMag-meanFreq())"
