Data Codebook for Coursera Getting and Cleaning Data Course Project

The R script run_analysis.R downloads raw data as a zip file, loads all necessary data into R, and processes it to create the tidy data output file tidydata.txt.

Study Design

Experiments were carried out based on a group of 30 volunteers that were within an age bracket of 19-48 years, irrespective of gender. 
Each individual performed six activities (walking, walking upstairs, walking downstairs, sitting, standing, and laying) while he/she was wearing a smartphone on his/her waist. 
Using an accelerometer and gyroscope embedded into the cellphone, both a 3-axial linear acceleration (tAcc-XYZ) and a 3-axial angular velocity (tGyro-XYZ) time domain signals were captured at a constant 50Hz rate. 

The dataset had been randomly partitioned into two disparate sets, where 70% of the volunteers were selected for generating the training dataset and 30% were selected for generating the test dataset.

The sensor signals were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a low-pass filter into body acceleration and gravity [tBodyAcc-XYZ, tGravityAcc-XYZ]. 

The gravitational force only has low frequency components, thus a 0.3 Hz cutoff frequency for the filter was used.

Subsequently, the body linear acceleration and angular velocity were calculated in order to obtain the proper Jerk signals [tBodyAccJerk-XYZ, tBodyGyroJerk-XYZ]. Also the magnitude of these three-dimensional signals were calculated using the Euclidean norm (tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag, tBodyGyroJerkMag).

Finally, a Fast Fourier Transform was applied to certain signals [fBodyAcc-XYZ, fBodyAccJerk-XYZ, fBodyGyro-XYZ, fBodyAccJerkMag, fBodyGyroMag, fBodyGyroJerkMag]

This produced the following list of signals, where the X, the Y, and the Z of '.XYZ' is used to denote the corresponding 3-axial signal direction
•	tBodyAcx.XYZ
•	tGravityAcc.XYZ
•	tBodyAccJerk.XYZ
•	tBodyGyro.XYZ
•	tBodyGyroJerk.XYZ
•	tBodyAccMag
•	tGravityAccMag
•	tBodyAccJerkMag
•	tBodyGyroMag
•	tBodyGyroJerkMag
•	fBodyAcc.XYZ
•	fBodyAccJerk.XYZ
•	fBodyGyro.XYZ
•	fBodyAccMag
•	fBodyAccJerkMag
•	fBodyGyroMag
•	fBodyGyroJerkMag

We restricted our analysis to 2 of these variables: the signal mean and the signal standard deviation. The variables used will end in the prefix corresponding to ".mean" or ".std"

The complete list of variables in the output tidy dataset tidydata.txt is shown below.
•	"activity" - this is the activity type, which is one of 6 types: walking, walking upstairs, walking downstairs, sitting, standing, or laying
•	"average.tBodyAcc.mean.X"
•	"average.tBodyAcc.mean.Y"
•	"average.tBodyAcc.mean.Z"
•	"average.tBodyAcc.std.X"
•	"average.tBodyAcc.std.Y"
•	"average.tBodyAcc.std.Z"
•	"average.tBodyAccJerk.mean.X"
•	"average.tBodyAccJerk.mean.Y"
•	"average.tBodyAccJerk.mean.Z"
•	"average.tBodyAccJerk.std.X"
•	"average.tBodyAccJerk.std.Y"
•	"average.tBodyAccJerk.std.Z"
•	"average.tBodyGyro.mean.X"
•	"average.tBodyGyro.mean.Y"
•	"average.tBodyGyro.mean.Z"
•	"average.tBodyGyro.std.X"
•	"average.tBodyGyro.std.Y"
•	"average.tBodyGyro.std.Z"
•	"average.tBodyGyroJerk.mean.X"
•	"average.tBodyGyroJerk.mean.Y"
•	"average.tBodyGyroJerk.mean.Z"
•	"average.tBodyGyroJerk.std.X"
•	"average.tBodyGyroJerk.std.Y"
•	"average.tBodyGyroJerk.std.Z"
•	"average.tBodyAccMag.mean"
•	"average.tBodyAccMag.std"
•	"average.tGravityAccMag.mean"
•	"average.tGravityAccMag.std"
•	"average.tBodyAccJerkMag.mean"
•	"average.tBodyAccJerkMag.std"
•	"average.tBodyGyroMag.mean"
•	"average.tBodyGyroMag.std"
•	"average.tBodyGyroJerkMag.mean"
•	"average.tBodyGyroJerkMag.std"
•	"average.fBodyAcc.mean.X"
•	"average.fBodyAcc.mean.Y"
•	"average.fBodyAcc.mean.Z"
•	"average.fBodyAcc.std.X"
•	"average.fBodyAcc.std.Y"
•	"average.fBodyAcc.std.Z"
•	"average.fBodyAccJerk.mean.X"
•	"average.fBodyAccJerk.mean.Y"
•	"average.fBodyAccJerk.mean.Z"
•	"average.fBodyAccJerk.std.X"
•	"average.fBodyAccJerk.std.Y"
•	"average.fBodyAccJerk.std.Z"
•	"average.fBodyGyro.mean.X"
•	"average.fBodyGyro.mean.Y"
•	"average.fBodyGyro.mean.Z"
•	"average.fBodyGyro.std.X"
•	"average.fBodyGyro.std.Y"
•	"average.fBodyGyro.std.Z"
•	"average.fBodyAccMag.mean"
•	"average.fBodyAccMag.std"
•	"average.tGravityAcc.mean.X"
•	"average.tGravityAcc.mean.Y"
•	"average.tGravityAcc.mean.Z"
•	"average.tGravityAcc.std.X"
•	"average.tGravityAcc.std.Y"
•	"average.tGravityAcc.std.Z"
•	"average.fBodyBodyAccJerkMag.mean"
•	"average.fBodyBodyAccJerkMag.std"
•	"average.fBodyBodyGyroMag.mean"
•	"average.fBodyBodyGyroMag.std"
•	"average.fBodyBodyGyroJerkMag.mean"
•	"average.fBodyBodyGyroJerkMag.std"
•	"n.observations" - this is the total num. of observations for subject and activity
•	"subject" - this is the subject number; there are 30 sequentially numbered subjects.
