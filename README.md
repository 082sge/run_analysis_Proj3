---
title: "README.md"
author: "Dexter Zulu"
date: "21/05/2020"
output: html_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

## Getting and Cleaning Data Course Project graded by my peers
This repository is a 082ge submission for Getting and Cleaning Data course project. It has the instructions on how to run analysis on Human Activity recognition dataset downloaded from the web.

## Dataset
Human Activity Recognition Using Smartphones and the file link is in my codebook.md

## Files
- CodeBook.md  a code book that describes the variables, the data, and any transformations or work that I performed to clean up the data

- Run_analysis.R  performs the data preparation and then followed by the 5 steps required as described in the course project’s definition:
  1. Merges the training and the test sets to create one data set.
  2. Extracts  only the measurements on the mean and standard deviation for each measurement.
  3. Uses  descriptive activity names to name the activities in the data set.
  4. Appropriately labels the data set with descriptive variable names.
  5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.
- FinalData.txt  is the exported tidy file as per instructions for the Project# Run_analysis
