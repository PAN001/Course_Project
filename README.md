# R scipt description

### description of implementation:

The R script uses two library package: library(dplyr) and library(tidyr)

1. first of all, get the working directory of the user and set several directories:

2. Load the required file and write them into several variables

3. Step 1: merge test_set and train_set into one table called sets
  
4. Step 2: extract any measurements related to mean and std
    
5. Step 3: merge the two acticity tables and add merge them into first_extract
    
6. Step 4: Appropriately labels the data set with descriptive variable names
    
7. Step 5: creates a second, independent tidy data set with the average of each variable for each activity and each subject.

### description of output:

The output is a text file with four columns "subject" "activity" "sensor" "mean" and 14221 rows;

There are totally 30 subjects, each is involved in 6 activities: 
1 WALKING
2 WALKING_UPSTAIRS
3 WALKING_DOWNSTAIRS
4 SITTING
5 STANDING
6 LAYING

There are 81 different measurements related to std and mean for each activity

Each variable is in one column, and each different observation of that variable is in a different row.

The result perfectly follows the standard of the tidy data.
