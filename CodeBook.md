

The run_analysis.R script performs the data gathering and then followed by the required operations

first, download the dataset
    link to the dataset used: https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip
    dataset downloaded and extracted under the folder called "UCI HAR Dataset"

    first, download the dataset
    
        link to the dataset used: https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip
        dataset downloaded and extracted under the folder called "UCI HAR Dataset"

    next, assigning each data to variables
    
        features <- features.txt
        
        activities <- activity_labels.txt 
       
        subject_test <- test/subject_test.txt 
        
        x_test <- test/X_test.txt 
        
        y_test <- test/y_test.txt 
        
        subject_train <- test/subject_train.txt
       
        x_train <- test/X_train.txt 
        
        y_train <- test/y_train.txt 
        

    1) merges the training and the test sets to create one data set
    
        x_merge created by merging x_train and x_test using rbind() function
        y_merge created by merging y_train and y_test using rbind() function
        subject_merge created by merging subject_train and subject_test using rbind() function
        merged_data created by merging subject_merge, y_merge and x_merge using cbind() function

    2) extracts only the measurements on the mean and standard deviation for each measurement
    
        tidy_data created by subsetting merged_data, selecting only columns: subject, code and the measurements on the mean and standard deviation (std) for each measurement

    3) uses descriptive activity names to name the activities in the data set
    
        entire numbers in code column of the tidy_data replaced with corresponding activity taken from second column of the activities variable

    4) appropriately labels the data set with descriptive variable names
    
        code column in tidy_data renamed into activities
        all Acc in column’s name replaced by Accelerometer
        all Gyro in column’s name replaced by Gyroscope
        all BodyBody in column’s name replaced by Body
        all Mag in column’s name replaced by Magnitude
        all start with character f in column’s name replaced by Frequency
        all start with character t in column’s name replaced by Time

    5) from the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject
        final_data created by sumarizing tidy_data taking the means of each variable for each activity and each subject, after groupped by subject and activity.
        
        


