# 3-Getting-and-Cleaning-Data-Project
### This code has been written according to the final Project of the getting and cleaning data course on Corsera by Jhon Hopkins University which is course 3 out of 10 courses in a Data science specialization.
### I have pasted the code here with comments describing what each step does 
### I will first describe the steps here: 
- We first download the data, store it in a folder called "data" after unzipping it. 
- We then read all the data that we are going to work on
- We bind the Training and Testing's data toghter binding the Subject, activity labels and the features in one data frame then binding  Both the training and testing data togther
- We then Add the feature names to the newly created data frame "containing all the data" as well as adding the "Subject" and "Activity" column names to the data frame accordingly. 
- We then need to change the Activity lables from 1-6 to more meaningfull names, to their actual names countained in the features.txt, We do so by first converting them to factors then changing the factor level's names according to those found in the features.txt file. 
- I have to note that I used this way of chnaging the names because I found it to be easy, yet there are ofcourse other way to do it. 
- Ok now we only have to fetch  the columns containing "Mean" and "STD" using grep and assign them  to a new data frame 
- Here we have a tidey well defined data  which we will need to take the means of each column according to each "subject" per each "activity" 
- We use the aggregate function to do so as shown below
- Now our final created data frame needs its names chnaged, thus we add "Mean Of(...)" to the original names of the columns referred to as "...". 

### Here is the commented code:
```
 if (!file.exists("./Data")) {dir.create("./Data")} #Creates a new folder called Data if it doesn't already exisit in the current working directory 
 download.file("https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip", destfile = "../Data.zip") Downloads the data files to the working directory out side the Data folder
 unzip(zipfile = "../Data.zip", exdir = "./Data") #unzips the data downloaded and stores it in the Data folder 
 setwd("./Data/UCI HAR Dataset") #sets the working directory to the unziped data folder 
 Xtrain <- read.table ("./train/X_train.txt") # Reads the X_Train data
 ytrain <- read.table("./train/y_train.txt") # Reads the y_Train data
 Strain <- read.table ("./train/subject_train.txt") # Reads the Subject Train data
 Xtest <- read.table("./test/X_test.txt") # Reads the X_test data 
 ytest <- read.table("./test/y_test.txt") # Reads the y_test data 
 Stest <- read.table("./test/subject_test.txt") # Reads the subject test data 
 features <- read.table("features.txt") # Reads the feature data
 Alables <- read.table("activity_labels.txt") # Reads the activity label data
 library(dplyr) # calls the dplyr library 
 BindTrain <- bind_cols(Strain,ytrain,Xtrain) # Bind the train data togther putting the subject forst then activity then the rest of the data
 BindTest <- bind_cols(Stest,ytest,Xtest) # Bind the test data togther putting the subject forst then activity then the rest of the data
 BindData <- bind_rows(BindTest, BindTrain) # Bind the Test and Train data row wise
 features <- as.matrix(features[,2]) # The feature data has 2 columns, we only need the second one and we store it in a matrix to avoid problems later on
 f <- t(cbind("Subject","Activity")) # we create a vector containing the column names for Subject and Activity 
 features <- rbind(f,features) # Here we create a vector/row(matrix) containing the updated feature vector using (row bind) 
 names(BindData) <- features   # Here we assign our BindData Data Frame its names 
 Mean_STD_Data <-  BindData[,grep("mean()|std()|Subject|Activity",names(BindData))] # We use grep to fetch all the mean and STD data "column numbers" then add subject and activity to be fetched as well, then we assign a new data frame with only the coulmns selected
 Mean_STD_Data[,2] <-  Mean_STD_Data[,2] %>% as.factor() # In order to change the activity variables from 1-6 to their names we first turn them into factors
 levels(Mean_STD_Data[,2]) <- Alables [,2] # the factor levels 1-6 can be chnaged to the actual name where Alables second column has the names
 Mean_Of_Tidy_Data <- aggregate(Mean_STD_Data[,3:length(Mean_STD_Data)], list(Subject = Mean_STD_Data$Subject, Activity = Mean_STD_Data$Activity), FUN = mean) # aggregate here applys the mean function to all the columns 3:81 per subject per activity of each subject
 Mean_Of_Tidy_Data <- arrange(Mean_Of_Tidy_Data, Subject) #We rearrange the out put data according to each subject 1-30
 New_Names <-  paste( "Mean Of (" , names ( Mean_Of_Tidy_Data[,3:length(Mean_Of_Tidy_Data)]),")", sep = "") #We cretae new names to add "Mean Of (...)" to explain the meaning of the new variables created.
 names(Mean_Of_Tidy_Data)[3:length(Mean_Of_Tidy_Data)] <- New_Names # We as asign the new names to the data frame (Mean_Of_Tidy_Data)
 write.table(Mean_Of_Tidy_Data , file = "./TideyData.txt", row.names = FALSE) 
```
