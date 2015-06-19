Getting and Cleaning Data    Course Project Design CodeBook

Study Design
This project read in data from the human activity movement study.....   







CodeBook
Variables
 names(resultsJoins)
 [1] "activityId"      Numeric identifier of activity id        
               "activityName"     Name of activity
 [3] "subjectId"          subject id for participant

Time based variables
BodyAcc is 
mean - is average
-std is standard deviation
-X,-Y-Z are 3 dimensional movements detected by accelerometer

   "time_BodyAcc-mean-X"              
 [5] "time_BodyAcc-mean-Y"         
           "time_BodyAcc-mean-Z"                   
 [7] "time_BodyAcc-std-X"         
            "time_BodyAcc-std-Y"                    
 [9] "time_BodyAcc-std-Z"             
        "time_GravityAcc-mean-X"                
[11] "time_GravityAcc-mean-Y"   
              "time_GravityAcc-mean-Z"                
[13] "time_GravityAcc-std-X"         
         "time_GravityAcc-std-Y"                 
[15] "time_GravityAcc-std-Z"        
          "time_BodyAccJerk-mean-X"               
[17] "time_BodyAccJerk-mean-Y"   
             "time_BodyAccJerk-mean-Z"               
[19] "time_BodyAccJerk-std-X"      
           "time_BodyAccJerk-std-Y"                
[21] "time_BodyAccJerk-std-Z"     
            "time_BodyGyro-mean-X"                  
[23] "time_BodyGyro-mean-Y"    
            "time_BodyGyro-std-Y"                   
[27] "time_BodyGyro-std-Z"    
                "time_BodyGyroJerk-mean-X"              
[29] "time_BodyGyroJerk-mean-Y"   
            "time_BodyGyroJerk-mean-Z"              
[31] "time_BodyGyroJerk-std-X"    
            "time_BodyGyroJerk-std-Y"               
[33] "time_BodyGyroJerk-std-Z"   
             "time_BodyAccMag-mean"                  
[35] "time_BodyAccMag-std"        
           "time_GravityAccMag-mean"               
[37] "time_GravityAccMag-std"       
          "time_BodyAccJerkMag-mean"              
[39] "time_BodyAccJerkMag-std"    
            "time_BodyGyroMag-mean"                 
[41] "time_BodyGyroMag-std"         
          "time_BodyGyroJerkMag-mean"     

Frequency based variables        
[43] "time_BodyGyroJerkMag-std"        
       "frequency_BodyAcc-mean-X"              
[45] "frequency_BodyAcc-mean-Y"     
          "frequency_BodyAcc-mean-Z"              
[47] "frequency_BodyAcc-std-X"     
           "frequency_BodyAcc-std-Y"               
[49] "frequency_BodyAcc-std-Z"    
            "frequency_BodyAcc-meanFreq-X"          
[51] "frequency_BodyAcc-meanFreq-Y"      
     "frequency_BodyAcc-meanFreq-Z"          
[53] "frequency_BodyAccJerk-mean-X"      
     "frequency_BodyAccJerk-mean-Y"          
[55] "frequency_BodyAccJerk-mean-Z"    
       "frequency_BodyAccJerk-std-X"           
[57] "frequency_BodyAccJerk-std-Y"    
        "frequency_BodyAccJerk-std-Z"           
[59] "frequency_BodyAccJerk-meanFreq-X" 
      "frequency_BodyAccJerk-meanFreq-Y"      
[61] "frequency_BodyAccJerk-meanFreq-Z"  
     "frequency_BodyGyro-mean-X"             
[63] "frequency_BodyGyro-mean-Y"   
          "frequency_BodyGyro-mean-Z"             
[65] "frequency_BodyGyro-std-X"   
            "frequency_BodyGyro-std-Y"              
[67] "frequency_BodyGyro-std-Z"      
         "frequency_BodyGyro-meanFreq-X"         
[69] "frequency_BodyGyro-meanFreq-Y"   
       "frequency_BodyGyro-meanFreq-Z"         
[71] "frequency_BodyAccMag-mean"        
      "frequency_BodyAccMag-std"              
[73] "frequency_BodyAccMag-meanFreq"    
      "frequency_BodyBodyAccJerkMag-mean"     
[75] "frequency_BodyBodyAccJerkMag-std"    
   "frequency_BodyBodyAccJerkMag-meanFreq" 
[77] "frequency_BodyBodyGyroMag-mean"     
    "frequency_BodyBodyGyroMag-std"         
[79] "frequency_BodyBodyGyroMag-meanFreq"   
80  "frequency_BodyBodyGyroJerkMag-mean"    
[81] "frequency_BodyBodyGyroJerkMag-std"      "frequency_BodyBodyGyroJerkMag-meanFreq"
