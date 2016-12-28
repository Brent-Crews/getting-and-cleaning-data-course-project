---title: "getting-and-cleaning-data-course-project"---

## Markdown
## 1. Merges the training and the test sets to create one data set.
### Loading packages (data.table hadn't been installed yet on my RStudio instance)
```{r}
setwd("/Users/brecre01/Documents/Coursera/getting-and-cleaning-data-course-project")
library(data.table)library(plyr)
```
### Loading in from raw data files
```{r}
subject_train = read.table('./train/subject_train.txt',header=FALSE)
x_train = read.table('./train/x_train.txt',header=FALSE)
y_train = read.table('./train/y_train.txt',header=FALSE)
subject_test = read.table('./test/subject_test.txt',header=FALSE)
x_test = read.table('./test/x_test.txt',header=FALSE)
y_test = read.table('./test/y_test.txt',header=FALSE)
```
### Merging initial data sets into a larger set
```{r}
x_dataset <- rbind(x_train, x_test)
y_dataset <- rbind(y_train, y_test)
subject_dataset <- rbind(subject_train, subject_test)
```

## 2. Extracts only the measurements on the mean and standard deviation for each measurement.
```{r}
x_dataset_mean_std <- x_dataset[, grep("-(mean|std)\\(\\)", read.table("features.txt")[, 2])]
names(x_dataset_mean_std) <- read.table("features.txt")[grep("-(mean|std)\\(\\)", read.table("features.txt")[, 2]), 2]
View(x_dataset_mean_std)
```
## 3. Uses descriptive activity names to name the activities in the data set
```{r}
y_dataset[, 1] <- read.table("activity_labels.txt")[y_dataset[, 1], 2]
names(y_dataset) <- "Activity"View(y_dataset)
```

## 4. Appropriately labels the data set with descriptive variable names.
```{r}
names(subject_dataset) <- "Subject"
```
### Merging initial data sets into a larger set
```{r}
all_in_one_dataset <- cbind(x_dataset_mean_std, y_dataset, subject_dataset)
```
### Labelling representative names corresponding to the full set of variables
```{r}
names(all_in_one_dataset) <- make.names(names(all_in_one_dataset))
names(all_in_one_dataset) <- gsub('Acc',"Acceleration",names(all_in_one_dataset))
names(all_in_one_dataset) <- gsub('Freq\\.',"Frequency.",names(all_in_one_dataset))
names(all_in_one_dataset) <- gsub('Freq$',"Frequency",names(all_in_one_dataset))
names(all_in_one_dataset) <- gsub('GyroJerk',"AngularAcceleration",names(all_in_one_dataset))
names(all_in_one_dataset) <- gsub('Gyro',"AngularSpeed",names(all_in_one_dataset))
names(all_in_one_dataset) <- gsub('Mag',"Magnitude",names(all_in_one_dataset))
names(all_in_one_dataset) <- gsub('^t',"TimeDomain.",names(all_in_one_dataset))
names(all_in_one_dataset) <- gsub('^f',"FrequencyDomain.",names(all_in_one_dataset))
names(all_in_one_dataset) <- gsub('\\.mean',".Mean",names(all_in_one_dataset))
names(all_in_one_dataset) <- gsub('\\.std',".StandardDeviation",names(all_in_one_dataset))
```

## 5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.
```{r}
data_out<-aggregate(. ~Subject + Activity, all_in_one_dataset, mean)
data_out<-data_out[order(data_out$Subject,data_out$Activity),]
write.table(data_out, file = "tidydata.txt",row.name=FALSE)```
