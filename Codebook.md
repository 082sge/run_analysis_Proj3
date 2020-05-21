---
title: "CodeBook.md"
author: "Dexter Zulu"
date: "21/05/2020"
output: html_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

This is the codebook for my assignment.

The <font size=”1”>run_analysis.R</font> script performs the data preparation and then followed by the 5 steps required as described in the course project’s definition.

## Download the dataset
-	Dataset  downloaded from the web (https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip) and extracted under the folder called UCI HAR Dataset in my Coursera folder

## Assign each data to variables
-	<font size=”1”>features <- features.txt :</font>  561 rows, 2 columns. The   features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ.
-	<font size=”1”>activities <- activity_labels.txt :</font>  6 rows, 2 columns

## List of activities performed when the corresponding measurements were taken and its codes (labels)
-	<font size=”1”>subject_test <- test/subject_test.txt :</font>  2947 rows, 1 column contains test data of 9/30 volunteer test subjects being observed
-	<font size=”1”>x_test <- test/X_test.txt :</font>  2947 rows, 561 columns contains recorded features test data
-	<font size=”1”>y_test <- test/y_test.txt :</font>  2947 rows, 1 columns contains test data of activities’ code labels
-	<font size=”1”>subject_train <- test/subject_train.txt :</font>  7352 rows, 1 column contains train data of 21/30 volunteer subjects being observed
-	<font size=”1”>x_train <- test/X_train.txt :</font>  7352 rows, 561 columns contains recorded features train data
-	<font size=”1”>y_train <- test/y_train.txt :</font>  7352 rows, 1 columns contains train data of activities’ code labels

## Step 1. Merges the training and the test sets to create one data set
-	<font size=”1”>X</font>  is created by merging <font size=”1”>x_train</font> and <font size=”1”>x_test</font> using <font size=”1”>rbind() function</font>
-	<font size=”1”>Y</font>  is created by merging <font size=”1”>y_train</font> and <font size=”1”>y_test</font> using <font size=”1”>rbind() function</font>
-	Subject  is created by merging <font size=”1”>subject_train and <font size=”1”>subject_test</font> using <font size=”1”>rbind() function</font>
-	<font size=”1”>Merged_Data</font>  is created by merging <font size=”1”>Subject, Y and X</font> using <font size=”1”>cbind() function</font>

## Step 2. Extracts only the measurements on the mean and standard deviation for each measurement
-	TidyData  is created by subsetting <font size=”1”>Merged_Data</font>, selecting only columns: <font size=”1”>subject, code and the measurements</font> on the <font size=”1”>mean and standard deviation (std)</font> for each measurement

## Step 3. Uses descriptive activity names to name the activities in the data set
-	Entire  numbers in code column of the TidyData replaced with corresponding activity taken from second column of the activities variable

## Step 4. Appropriately  labels the data set with descriptive variable names code column in TidyData renamed into activities
-	All  Acc in column’s name replaced by Accelerometer

-	All  Gyro in column’s name replaced by Gyroscope

-	All  BodyBody in column’s name replaced by Body

-	All  Mag in column’s name replaced by Magnitude

-	All  start with character f in column’s name replaced by Frequency

-	All start  with character t in column’s name replaced by Time

## Step 5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject
-	FinalData  file is created by summarizing TidyData taking the means of each variable for each activity and each subject, after grouped by subject and activity.
-	Export  FinalData file into a text, <font size=”1”>FinalData.txt</font>.


Note that the `echo = FALSE` parameter was added to the code chunk to prevent printing of the R code that generated the plot.
