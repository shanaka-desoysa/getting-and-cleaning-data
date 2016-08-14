# Human Activity Recognition Using Smartphones Dataset Raw Data
The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain. See 'features_info.txt' for more details. 

## For each record it is provided:

- Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration.
- Triaxial Angular velocity from the gyroscope. 
- A 561-feature vector with time and frequency domain variables. 
- Its activity label. 
- An identifier of the subject who carried out the experiment.

## Acknowledgement

[1] Davide Anguita, Alessandro Ghio, Luca Oneto, Xavier Parra and Jorge L. Reyes-Ortiz. Human Activity Recognition on Smartphones using a Multiclass Hardware-Friendly Support Vector Machine. International Workshop of Ambient Assisted Living (IWAAL 2012). Vitoria-Gasteiz, Spain. Dec 2012

This dataset is distributed AS-IS and no responsibility implied or explicit can be addressed to the authors or their institutions for its use or misuse. Any commercial use is prohibited.

Jorge L. Reyes-Ortiz, Alessandro Ghio, Luca Oneto, Davide Anguita. November 2012.

http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

## Raw Data
http://archive.ics.uci.edu/ml/machine-learning-databases/00240/

# Tidy Data
The objective of this project is to clean up the Raw data from the above mentioned publication. 
R script  run_analysis.R has been created for this purpose.

## Getting Data
- Create . /data folder
- Download zip file from https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip
- Unzip zip file to ./data folder
- Read Test dataset with labels to “subject”, “y” and “x” data frames
- Read Training dataset with labels to “subject”, “y” and “x” data frames

## 1. Merges the training and the test sets to create one data set.
Use cbind() function to bind “subject”, “y” and “x” data frames created in previous step and create “test” and “train” data frames.
Use rbind() function to merge “test” and “train” data frames
Remove unnecessary objects.

## 2. Extracts only the measurements on the mean and standard deviation for each measurement.
Use grepl() to filter the columns matching “mean”, “std”,  “Activity”, and “Subject".

## 3. Uses descriptive activity names to name the activities in the data set
Read “activity_labels.txt” to obtain activity names. Use factor() method to set the activity labels

## 4. Appropriately labels the data set with descriptive variable names.
Use sub() method to fix column names.

## 5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.
Use plyr package to get a tidy data set with the average of each variable for each activity and each subject.
Write tidy data set to file “./data/tidyData.txt”.

