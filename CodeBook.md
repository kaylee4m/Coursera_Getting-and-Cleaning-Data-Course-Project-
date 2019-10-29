# Code Book
This project include these following steps:
* Dataset downloaded and extracted under the folder called `UCI HAR Dataset`

* Assign each data to variables
   * `features` <- `features.txt` : 561 rows, 2 columns
   * `activities` <- `activity_labels.txt` : 6 rows, 2 columns
   * `subject_test` <- `test/subject_test.txt` : 2947 rows, 1 column
   * `x_test` <- `test/X_test.txt` : 2947 rows, 561 columns
   * `y_test` <- `test/y_test.txt` : 2947 rows, 1 columns
   * `subject_train` <- `test/subject_train.txt` : 7352 rows, 1 column
   * `x_train` <- `test/X_train.txt` : 7352 rows, 561 columns
   * `y_train` <- `test/y_train.txt` : 7352 rows, 1 columns

* Merges the training and the test sets to create one data set
   *`X` and `Y` are created by merging x_train and x_test, y_train and y_test using `rbind() function`
   *`Subject` is created by merging subject_train and subject_test using `rbind() function`
   *`Merged_Data` is created by merging Subject, Y and X using `cbind() function`
   *`TidyData` is created by subsetting Merged_Data, selecting only columns: subject, code and the measurements on the mean and standard deviation (std) for each measurement


* Appropriately labels the data set with descriptive variable names
   *code column in TidyData renamed into ` activities` 
   *` Acc`  in column’s name replaced by ` Accelerometer` 
   *` Gyro`  in column’s name replaced by ` Gyroscope` 
   *` BodyBody`  in column’s name replaced by ` Body` 
   *` Mag`  in column’s name replaced by ` Magnitude` 
   *All start with ` f`  in column’s name replaced by ` Frequency` 
   *All start with ` t`  in column’s name replaced by ` Time` 


* ` FinalData` is created by sumarizing ` TidyData`  taking the means of each variable for each activity and each subject, after groupped by subject and each subject, after groupped by subject and activity.
