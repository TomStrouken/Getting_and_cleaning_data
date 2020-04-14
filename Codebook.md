
## Dataset and preperation

The Run_analysis.R script will download the dataset URI HAR Dataset and prepares it to a tidy dataset names PreparedData. This script contains data preparation, and 5 steps to create the tidy dataset.

Out of each textfile in the dataset there where 8 objects created:
- features <- features.txt : 561 rows, 2 columns 
- activity_labels <- activity_labels.txt : 6 rows, 2 columns 
- subject_test <- test/subject_test.txt : 2947 rows, 1 column 
- x_test <- test/X_test.txt : 2947 rows, 561 columns 
- y_test <- test/y_test.txt : 2947 rows, 1 columns 
- subject_train <- test/subject_train.txt : 7352 rows, 1 column 
- x_train <- test/X_train.txt : 7352 rows, 561 columns 
- y_train <- test/y_train.txt : 7352 rows, 1 columns 

## Merge objects
Out of the objects there where 3 objects created:
- X : 10299 rows, 561 columns <- merge x_train and x_test using rbind()
- Y : 10299 rows, 1 column <- merge y_train and y_test using rbind()
- Subject : 10299 rows, 1 column <- merge subject_train and subject_test using rbind()

These 3 objects merged together form the last object, the merged dataset:
- Merged_Data : 10299 rows, 563 column <- merge Subject, X and Y using cbind()

## Extract measurment
The Merged_Data is subsetted selecting coloms subject, code and the measurements of the mean and std of each measurement. Out of this subsetting TidyData is created. 

## Descriptive activity names
The numbers in the variable called code, in the TidyData, have been replaced by the names in the activities variable.

## Labels
The labels in the dataset have been renamed into appropriate labels.

## Independent dataset
By summarizing TidyData the final dataset, PreparedData : 180 rows, 88 coloms, has been created and exported to the PreparedData.txt file. 

