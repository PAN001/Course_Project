# DATA DICTIONARY

## Original source information:
==================================================================
Human Activity Recognition Using Smartphones Dataset
Version 1.0
==================================================================
Jorge L. Reyes-Ortiz, Davide Anguita, Alessandro Ghio, Luca Oneto.
Smartlab - Non Linear Complex Systems Laboratory
DITEN - Universit‡ degli Studi di Genova.
Via Opera Pia 11A, I-16145, Genoa, Italy.
activityrecognition@smartlab.ws
www.smartlab.ws
==================================================================
License:
========
Use of this dataset in publications must be acknowledged by referencing the following publication [1] 

[1] Davide Anguita, Alessandro Ghio, Luca Oneto, Xavier Parra and Jorge L. Reyes-Ortiz. Human Activity Recognition on Smartphones using a Multiclass Hardware-Friendly Support Vector Machine. International Workshop of Ambient Assisted Living (IWAAL 2012). Vitoria-Gasteiz, Spain. Dec 2012

This dataset is distributed AS-IS and no responsibility implied or explicit can be addressed to the authors or their institutions for its use or misuse. Any commercial use is prohibited.

Jorge L. Reyes-Ortiz, Alessandro Ghio, Luca Oneto, Davide Anguita. November 2012.

## Experiment description:
The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain.

## General description:
The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ. These time domain signals (prefix 't' to denote time) were captured at a constant rate of 50 Hz. Then they were filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. Similarly, the acceleration signal was then separated into body and gravity acceleration signals (tBodyAcc-XYZ and tGravityAcc-XYZ) using another low pass Butterworth filter with a corner frequency of 0.3 Hz. 

Subsequently, the body linear acceleration and angular velocity were derived in time to obtain Jerk signals (tBodyAccJerk-XYZ and tBodyGyroJerk-XYZ). Also the magnitude of these three-dimensional signals were calculated using the Euclidean norm (tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag, tBodyGyroJerkMag). 

Finally a Fast Fourier Transform (FFT) was applied to some of these signals producing fBodyAcc-XYZ, fBodyAccJerk-XYZ, fBodyGyro-XYZ, fBodyAccJerkMag, fBodyGyroMag, fBodyGyroJerkMag. (Note the 'f' to indicate frequency domain signals). 

These signals were used to estimate variables of the feature vector for each pattern:  
'-XYZ' is used to denote 3-axial signals in the X, Y and Z directions.

## Variable general description:

Features are normalized and bounded within [-1,1]

###The set of variables that were estimated from these signals are: 
mean(): Mean value
std(): Standard deviation

###Additional vectors obtained by averaging the signals in a signal window sample. These are used on the angle() variable:
gravityMean
tBodyAccMean
tBodyAccJerkMean
tBodyGyroMean
tBodyGyroJerkMean

## Variable specific description:

###tBodyAcc_mean()_X                
###tBodyAcc_mean()_Y                
###tBodyAcc_mean()_Z                
###tBodyAcc_std()_X                
###tBodyAcc_std()_Y                 
###tBodyAcc_std()_Z                
###tGravityAcc_mean()_X             
###tGravityAcc_mean()_Y            
###tGravityAcc_mean()_Z             
###tGravityAcc_std()_X              
###tGravityAcc_std()_Y              
###tGravityAcc_std()_Z             
###tBodyAccJerk_mean()_X            
###tBodyAccJerk_mean()_Y            
###tBodyAccJerk_mean()_Z            
###tBodyAccJerk_std()_X            
###tBodyAccJerk_std()_Y             
###tBodyAccJerk_std()_Z             
###tBodyGyro_mean()_X               
###tBodyGyro_mean()_Y              
###tBodyGyro_mean()_Z              
###tBodyGyro_std()_X            
###tBodyGyro_std()_Y                
###tBodyGyro_std()_Z               
###tBodyGyroJerk_mean()_X           
###tBodyGyroJerk_mean()_Y           
###tBodyGyroJerk_mean()_Z           
###tBodyGyroJerk_std()_X           
###tBodyGyroJerk_std()_Y            
###tBodyGyroJerk_std()_Z            
###tBodyAccMag_mean()               
###tBodyAccMag_std()               
###tGravityAccMag_mean()            
###tGravityAccMag_std()            
###tBodyAccJerkMag_mean()           
###tBodyAccJerkMag_std()           
###tBodyGyroMag_mean()              
###tBodyGyroMag_std()               
###tBodyGyroJerkMag_mean()         
###tBodyGyroJerkMag_std()          
###fBodyAcc_mean()_X                
###fBodyAcc_mean()_Y               
###fBodyAcc_mean()_Z                
###fBodyAcc_std()_X                
###fBodyAcc_std()_Y                 
###fBodyAcc_std()_Z                 
###fBodyAcc_meanFreq()_X            
###fBodyAcc_meanFreq()_Y           
###fBodyAcc_meanFreq()_Z            
###fBodyAccJerk_mean()_X            
###fBodyAccJerk_mean()_Y            
###fBodyAccJerk_mean()_Z           
###fBodyAccJerk_std()_X             
###fBodyAccJerk_std()_Y             
###fBodyAccJerk_std()_Z            
###fBodyAccJerk_meanFreq()_X       
###fBodyAccJerk_meanFreq()_Y        
###fBodyAccJerk_meanFreq()_Z        
###fBodyGyro_mean()_X               
###fBodyGyro_mean()_Y             
###fBodyGyro_mean()_Z             
###fBodyGyro_std()_X                
###fBodyGyro_std()_Y                
###fBodyGyro_std()_Z               
###fBodyGyro_meanFreq()_X           
###fBodyGyro_meanFreq()_Y           
###fBodyGyro_meanFreq()_Z           
###fBodyAccMag_mean()              
###fBodyAccMag_std()                
###fBodyAccMag_meanFreq()           
###fBodyBodyAccJerkMag_mean()       
###fBodyBodyAccJerkMag_std()       
###fBodyBodyAccJerkMag_meanFreq()  
###fBodyBodyGyroMag_mean()          
###fBodyBodyGyroMag_std()           
###fBodyBodyGyroMag_meanFreq()     
###fBodyBodyGyroJerkMag_mean()      
###fBodyBodyGyroJerkMag_std()       
###fBodyBodyGyroJerkMag_meanFreq() 