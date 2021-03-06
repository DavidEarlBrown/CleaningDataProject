Getting and Cleaning Data    Course Project Design CodeBook

Study Design
This project read in data from the human activity movement study.....   



Per the readme text on the downloaded file the source data we imported was obtained as follows: 

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain. See 'features_info.txt' for more details. 

The data were obtained from the URL  https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip  this file was downloaded into the  GettingAndCleaningData/CourseProject folder and then unzipped.  The files were extracted by referencing them in the "../" folders above the R studio work space such as: 
read.table("../UCI HAR Dataset/test/X_test.txt")  other files were imported into R tables using the same folder structure.   See the comments in the run_analysis.R file in this git repository. 

The test and train file sets were each merged using rbind so that one large file with 10299 rows was created over both test and join data sets. 

Ther run_analysis.R file has comments with each step in the project analysis so that it can be run as a single autommated script with the comments providing all the CodeBook information necessary for this project.
CodeBook ==========================================================================
Variables
 The data were summarized and grouped by activityId and Subject Id as per project instructions 
 and the data were joined to the activity identifiers and subject ids where were in separate files.  These columns were included in the summarized report by using a join with a resulting dataFrame resultsJoins.

Note on Values:   Features are normalized and bounded within [-1,1] for each measurement identified.
 
 names(resultsJoins)
  "activityId"      Numeric identifier of activity id        
  "activityName"     Name of activity
   "subjectId"          subject id for participant

Time based variables
BodyAcc is 
mean - is average
-std is standard deviation
-X,-Y-Z are 3 dimensional movements detected by accelerometer
Acc is taken from Accelerometer measurements.
Gyro was taken from the Gyrometer measurements. 

Variables in result table starting with variable 4 after joined activityId,activityName and subjectId explained above.
 4  "time_BodyAcc-mean-X"     time interval BodyAccelerometer mean for X,Y,Z dimensions         
 5 "time_BodyAcc-mean-Y"         
 6  "time_BodyAcc-mean-Z"                   
 7 "time_BodyAcc-std-X"     time interval BodyAccelerometer std deviation for X,Y,Z dimensions     
 8 "time_BodyAcc-std-Y"                    
 9 "time_BodyAcc-std-Z"             
 10 "time_GravityAcc-mean-X"time interval Gravity MesurementsAccelerometer mean for X,Y,Z dimensions                
11 "time_GravityAcc-mean-Y"   
12  "time_GravityAcc-mean-Z"                
13 "time_GravityAcc-std-X"      time interval Gravity MesurementsAccelerometer standard deviation for X,Y,Z dimensions        
14 "time_GravityAcc-std-Y"                 
15 "time_GravityAcc-std-Z"        
16 "time_BodyAccJerk-mean-X" time interval BodyJerk Measurements Accelerometer mean for X,Y,Z                
17 "time_BodyAccJerk-mean-Y"   
18  "time_BodyAccJerk-mean-Z"               
19 "time_BodyAccJerk-std-X"   time interval BodyJerk Measurements Accelerometer std deviation for X,Y,Z     
20   "time_BodyAccJerk-std-Y"                
21 "time_BodyAccJerk-std-Z"     
22 "time_BodyGyro-mean-X"   time interval Body Gyrometer Measurements mean for X,Y dimensions                
23 "time_BodyGyro-mean-Y"    
24 "time_BodyGyro-std-Y"    time interval Body Gyrometer Measurements std deviation for Y,Z dimensions              

other   time interval Body Gyrometer Measurements mean for X,Z,Z dimensions where -mean is group mean and -std is group std deviation
25 "time_BodyGyro-std-Z"    
26 "time_BodyGyroJerk-mean-X"     
27 "time_BodyGyro-std-Z"                   
28 "time_BodyGyroJerk-mean-X"     
29 "time_BodyGyroJerk-mean-Y"   
30  "time_BodyGyroJerk-mean-Z"              
31 "time_BodyGyroJerk-std-X"    
32 "time_BodyGyroJerk-std-Y"               
33 "time_BodyGyroJerk-std-Z"   
   Accelerometer Mag measurements
34 "time_BodyAccMag-mean"                  
35 "time_BodyAccMag-std"        
36 "time_GravityAccMag-mean"               
37 "time_GravityAccMag-std"       
38 "time_BodyAccJerkMag-mean"              
39 "time_BodyAccJerkMag-std"    
40 "time_BodyGyroMag-mean"                 
41 "time_BodyGyroMag-std"         
42 "time_BodyGyroJerkMag-mean"     
43 "time_BodyGyroJerkMag-std" 

Frequency based variables  for same variables as above with same namng conventions       
       
 44 "frequency_BodyAcc-mean-X"              
45 "frequency_BodyAcc-mean-Y"     
56 "frequency_BodyAcc-mean-Z"              
47 "frequency_BodyAcc-std-X"     
48 "frequency_BodyAcc-std-Y"               
49 "frequency_BodyAcc-std-Z"    
50 "frequency_BodyAcc-meanFreq-X"          
51 "frequency_BodyAcc-meanFreq-Y"      
52 "frequency_BodyAcc-meanFreq-Z"          
53 "frequency_BodyAccJerk-mean-X"      
54 "frequency_BodyAccJerk-mean-Y"          
55 "frequency_BodyAccJerk-mean-Z"    
56 "frequency_BodyAccJerk-std-X"           
57 "frequency_BodyAccJerk-std-Y"    
58 "frequency_BodyAccJerk-std-Z"           
59 "frequency_BodyAccJerk-meanFreq-X" 
60 "frequency_BodyAccJerk-meanFreq-Y"      
61 "frequency_BodyAccJerk-meanFreq-Z"  
62 "frequency_BodyGyro-mean-X"             
63 "frequency_BodyGyro-mean-Y"   
64 "frequency_BodyGyro-mean-Z"             
65 "frequency_BodyGyro-std-X"   
66 "frequency_BodyGyro-std-Y"              
67 "frequency_BodyGyro-std-Z"      
68 "frequency_BodyGyro-meanFreq-X"         
69 "frequency_BodyGyro-meanFreq-Y"   
70 "frequency_BodyGyro-meanFreq-Z"         
71 "frequency_BodyAccMag-mean"        
72 "frequency_BodyAccMag-std"              
73 "frequency_BodyAccMag-meanFreq"    
74 "frequency_BodyBodyAccJerkMag-mean"     
75 "frequency_BodyBodyAccJerkMag-std"    
76 "frequency_BodyBodyAccJerkMag-meanFreq" 
77 "frequency_BodyBodyGyroMag-mean"     
78 "frequency_BodyBodyGyroMag-std"         
79 "frequency_BodyBodyGyroMag-meanFreq"   
80  "frequency_BodyBodyGyroJerkMag-mean"    
81 "frequency_BodyBodyGyroJerkMag-std"
82 "frequency_BodyBodyGyroJerkMag-meanFreq"
