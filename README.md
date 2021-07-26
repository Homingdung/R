# R

## Introduction

This is a case study by using linear model.

>  This course work is based on *MATH2011 Statistical Models and Methods*, School of Mathematical Sciences, University of Nottingham, UK
>  Lecturer:
>
>  + Autumn: Prof Frank Ball
>  + Spring: Dr Chris Fallaize
>  Thanks to Frank, who gives me lots of insights in theoretical knowledge, and Chris, who prepared lots of nice materials for us to touch many practical skills by R. 



## Usage

```Train.txt```  is used for modeling while ```Test.txt``` is used for prediction.

>  This data set is composed of 21 measured data about loan applicants, we will only treat Duration, Amount, Age as numerical variables while others will be treated as factors, since other types of variables are either factors or with a very small number of distinct possibilities they can take.

```R
# pre-processing for dataset
library(ggplot2)
library(dplyr)
library(carData)
library(car)

# Train.txt
Train<-read.table("Train.txt",header=T)
Train<-Train %>% mutate_if(is.character,as.factor)
Train$Disposable<-factor(Train$Disposable)
Train$OtherParties<-factor(Train$OtherParties)
Train$Residence<-factor(Train$Residence)
Train$Existing<-factor(Train$Existing)
Train$Dependants<-factor(Train$Dependants)
str(Train)

# Test.txt
Test<-read.table("Test.txt",header=T)
Test<-Test %>% mutate_if(is.character,as.factor)
Test$Disposable<-factor(Test$Disposable)
Test$OtherParties<-factor(Test$OtherParties)
Test$Residence<-factor(Test$Residence)
Test$Existing<-factor(Test$Existing)
Test$Dependants<-factor(Test$Dependants)
str(Test)
```

Run ```risk_analysis.Rmd``` in Rstudio to get more details.

![IMG_2707](https://user-images.githubusercontent.com/57780176/124998645-b12f5800-e044-11eb-851a-92c33a78ffdd.jpg)
