# Course_Project

The R script uses two library package: library(dplyr) and library(tidyr)

1. first of all, get the working directory of the user and set several directories:
    wd <- getwd()
    test_set_directory = paste(wd, "UCI HAR Dataset/test/X_test.txt", sep = "/")
    train_set_directory = paste(wd, "UCI HAR Dataset/train/X_train.txt", sep = "/")
    test_act_directory = paste(wd, "UCI HAR Dataset/test/y_test.txt", sep = "/")
    train_act_directory = paste(wd, "UCI HAR Dataset/train/y_train.txt", sep = "/")
    test_subject_directory = paste(wd, "UCI HAR Dataset/test/subject_test.txt", sep = "/")
    train_subject_directory = paste(wd, "UCI HAR Dataset/train/subject_train.txt", sep = "/")
    features_directory = paste(wd, "UCI HAR Dataset/features.txt", sep = "/")

2. Load the required file and write them into several variables
      ##load set file:
    test_set <- read.table(test_set_directory)
    train_set <- read.table(train_set_directory)
      ## load activity file
    test_act <- read.table(test_act_directory)
    train_act <- read.table(train_act_directory)
      ## loac subject file
    test_subject <- read.table(test_subject_directory)
    train_subject <- read.table(train_subject_directory)
      ## load features file
    features <- read.table(features_directory, stringsAsFactors=FALSE)

3.Step 1: merge test_set and train_set into one table called sets
  sets <- rbind(test_set, train_set)
  
4.Step 2: extract any measurements related to mean and std
    features_list <- features[,2]
    is_mean <- grepl("mean", features_list)
    is_std <- grepl("std", features_list)
    is_useful <- is_mean | is_std  ## length of extracted columns is 79
    features_names <- features_list[is_useful]  ## save the corresponding names
      ## extract the specific columns
    first_extract <- sets[,is_useful]  ## 10299 * 79
    
5.Step 3: merge the two acticity tables and add merge them into first_extract
    activities_column <- rbind(test_act, train_act)
      ## replace the numeric names in the activity file with the meaningful names
    name1 <- "WALKING"
    name2 <- "WALKING_UPSTAIRS"
    name3 <- "WALKING_DOWNSTAIRS"
    name4 <- "SITTING"
    name5 <- "STANDING"
    name6 <- "LAYING"
    activities_column[,1] <- sub(1, name1, activities_column[,1])
    activities_column[,1] <- sub(2, name2, activities_column[,1])
    activities_column[,1] <- sub(3, name3, activities_column[,1])
    activities_column[,1] <- sub(4, name4, activities_column[,1])
    activities_column[,1] <- sub(5, name5, activities_column[,1])
    activities_column[,1] <- sub(6, name6, activities_column[,1])  ## 10299 * 1
      ## use cbind to add activities_column into first_extract and new file is called table2
    table2 <- cbind(activities_column, first_extract)  ## 10299 * 80
    
6. Step 4: Appropriately labels the data set with descriptive variable names
    right_features_names <- gsub("-", "_", features_names)
    right_features_names <- gsub("\\(\\)", "", right_features_names)
    column_names <- c("activity", right_features_names)
    colnames(table2) <- column_names
    
7. Step 5: creates a second, independent tidy data set with the average of each variable for each activity and each subject.
      ## first of all, add the subject column 
    subject_column <- rbind(test_subject, train_subject)  ## 10299 * 1
    table3 <- cbind(subject_column, table2)  ## 10299 * 81
      ## name the first column(subject column)
    colnames(table3) = c("subject", column_names)
    
    ## use dplyr library
    library(dplyr)
    tidy_result <- tbl_df(table3)
    
    # use library(tidyr)
    library(tidyr)
    ttidy <- tidy_result %>%
      gather(sensor, Value, 3:81) ## 813261 * 4
    final_result <- ttidy %>%
      group_by(subject, activity, sensor) %>%
      summarize(mean = mean(Value))
    
    ## output the tidy table 
    write.csv(final_result, "final_data.csv", row.names = FALSE)
    write.table(final_result, "final_data.txt", row.name = FALSE)
