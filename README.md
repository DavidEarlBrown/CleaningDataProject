# CleaningDataProject
Repository for getting and cleaning data course project
# Getting and Cleaning Data Course Project Script
# Author:  David E Brown
# Name run_analysis.R
# Retrieve data sets into R data make data frames
# Instructions =============================================================================================
# Merge the training and test sets to create one data set.
# Extract only the mean and standard deviation for each measurement
# Use Descriptive activity names to name the activities in the data set
# Appropriately label the dataset with descriptive variable names
# create a second indepenent tidy  data with the average of ecah activity and each subject

# For each record in the dataset, the following is provided: 
#  - Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration. 
#- Triaxial Angular velocity from the gyroscope. 
#- A 561-feature vector with time and frequency domain variables. 
#- Its activity label. 
#- An identifier of the subject who carried out the experiment.
# steps for runbook ===================================================================================
# download data into Course/DataScience/GettingAndCleaningData/CourseProject Directory
# getdata-projectfiles-UCI HAR Dataset.zip
# on MacOSX expand zip file and create directories of text files for project ====================
# start load packages that may be needed =====
install.packages("data.table")
install.packages("dplyr")
library(data.table)
library(dplyr)
browseVignettes(package = "dplyr")
# 2 - read in data sets after downloaded and zip expanded read all files into data frames
# reference unzipped files one directopry up and place in workspace directory for R Studio:
df_test_subject <- read.table("../UCI HAR Dataset/test/subject_test.txt")
df_test_x <- read.table("../UCI HAR Dataset/test/X_test.txt")
df_test_y <- read.table("../UCI HAR Dataset/test/y_test.txt")
df_train_subject <- read.table("../UCI HAR Dataset/train/subject_train.txt")
df_train_y <- read.table("../UCI HAR Dataset/train/y_train.txt")
df_train_x <- read.table("../UCI HAR Dataset/train/x_train.txt")
# activity label ids to match with test_y and train_y  as well as combined_y
df_activity_labels <- read.table("../UCI HAR Dataset/activity_labels.txt")
# set up readable names using plyr
rename(df_activity_labels, c("V1"="activityId", "V2"="activityName"))
resultsJoins <- inner_join(activities,results) 
# get column names for x tables
df_features_cols <- read.table("../UCI HAR Dataset/features.txt")
# set colnames vector
names <-df_features_cols[,2]
# set column headings for x variables
colnames(df_test_x) <- names
colnames(df_train_x) <- names
# get inertial signals even though will not use them for averages ============================
# test data ================
df_test_body_acc_x <- read.table("../UCI HAR Dataset/test/Inertial Signals/body_acc_x_test.txt")
df_test_body_acc_y <- read.table("../UCI HAR Dataset/test/Inertial Signals/body_acc_y_test.txt")
df_test_body_gyro_x <- read.table("../UCI HAR Dataset/test/Inertial Signals/body_gyro_x_test.txt")
df_test_body_gyro_y <- read.table("../UCI HAR Dataset/test/Inertial Signals/body_gyro_y_test.txt")
df_test_body_gyro_z <- read.table("../UCI HAR Dataset/test/Inertial Signals/body_gyro_z_test.txt")
df_test_total_acc_x <- read.table("../UCI HAR Dataset/test/Inertial Signals/total_acc_x_test.txt")
df_test_total_acc_y <- read.table("../UCI HAR Dataset/test/Inertial Signals/total_acc_y_test.txt")
df_test_total_acc_z <- read.table("../UCI HAR Dataset/test/Inertial Signals/total_acc_z_test.txt")
df_test_body_acc_z <- read.table("../UCI HAR Dataset/test/Inertial Signals/body_acc_z_test.txt")
# training data   ===================
df_train_body_acc_y <- read.table("../UCI HAR Dataset/train/Inertial Signals/body_acc_y_train.txt")
df_train_body_acc_z <- read.table("../UCI HAR Dataset/train/Inertial Signals/body_acc_z_train.txt")
df_train_body_gyro_x <- read.table("../UCI HAR Dataset/train/Inertial Signals/body_gyro_x_train.txt")
df_train_body_gyro_y <- read.table("../UCI HAR Dataset/train/Inertial Signals/body_gyro_y_train.txt")
df_train_body_gyro_z <- read.table("../UCI HAR Dataset/train/Inertial Signals/body_gyro_z_train.txt")

df_train_total_acc_x <- read.table("../UCI HAR Dataset/train/Inertial Signals/total_acc_x_train.txt")
df_train_total_acc_y <- read.table("../UCI HAR Dataset/train/Inertial Signals/total_acc_y_train.txt")
df_train_total_acc_z <- read.table("../UCI HAR Dataset/train/Inertial Signals/total_acc_z_train.txt")
# combine x observations for training and test ===========================
df_combined_x <- rbind(df_test_x,df_train_x)
dim(df_combined_x)
# get combined activity for y (which is the activity id)
df_combined_y <- rbind(df_test_y,df_train_y)
# change named subject ids from y labels 
names(df_combined_y) <- c("subjectId")
# get combined subject no
df_combined_subject <- rbind(df_test_subject,df_train_subject)
# get mean and std deviation values from test and training results ============================
df_combined_x_mean_dev <- df_combined_x[,grep("mean|std", names(df_combined_x), value=TRUE)]
df_combined_with_subject_activity <- cbind(df_combined_subject,df_combined_y,df_combined_x_mean_dev)
# rename results set for shorter name - convenience only ==================================
df_results_dtl <- df_combined_with_subject_activity
r <- df_results_dtl
# rename columns
names(r) <- gsub("[()]", "", names(r))
names(r) <- gsub("^[t]", "time_", names(r))
names(r) <- gsub("^[f]", "frequency_", names(r))
# group by activityId and Subject Id get all averages   
dg=group_by(df_results_dtl,activityId,subjectId)

results <- summarise_each(dg,funs(mean))
# join tables so that activity names are displayed instead of just numbers
resultsJoins <- inner_join(activities,results)

# write out table of results as the result of joins for upload for course project. 
write.table(resultsJoins,"courseProjectResults.txt", row.name = FALSE)
