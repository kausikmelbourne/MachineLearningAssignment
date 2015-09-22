---
Title       : The Data Science - Machine Learning Project Assignment
Subtitle    : Prediction Assignment Writeup
Author      : K Samanta
---

## Overview
The goal of the project assignment is to predict the exercise manner categories from the sampl exercise training data. 
The variable name for prediction is "classe" and the other variables are used to predict "classe" value.
This report describes the steps to built the model, cross validation steps and the expected out of sample error.

## Defining Error Rate
There is no specific requirement for prediction accuracy rate. However, lets set an prediction eror rate to be less than 5%.

## Load Training/Test data and split training data for validation
The data loaded from the two .csv files provided. Followind is the R code for loading the data. 

library(caret) <BR>
trn <- read.csv("pml-training.csv", na.strings = c("NA", "", "#DIV/0!")) <BR>
tst <- read.csv("pml-testing.csv", na.strings = c("NA", "", "#DIV/0!")) <BR>

\#Split training data for validation set <BR>
trninx <-  createDataPartition( y = trn$classe, p = .8, list = FALSE ) <BR>
trnmod <- trn[trninx,] <BR>
trnvld <- trn[-trninx,] <BR>


## Select features/variables
The dataset contains 160 variable including the prediction variable. The following analysis has been performed to identify the appropriate variables. Following are codes for exploratory analysis including visualisations.


for (i in 1:160)
{
  print(i)
  plot(trn[,1], trn[,i], col = trn$classe, main = i)
  cat("Press Enter to continue ...")
  Ln <- readline()
}

featurePlot(x = trn[,c(1,7)], y = trn$classe, plot = "pairs")

plot(trn$X, trn$num_window, col = trn$classe, main = "X vs Num Window")

## Define the Model
After exploratory analysis, it is evident that the problem is related to clustering problem and looks the method random forest can be used for the model.


##Cross Validation and expected Out of Sample error 

##Prediction on Test data

## IMG

<img class=center src="../../assets/tst.png" height=400 />
