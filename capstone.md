# Case Study: How Can a Wellness Technology Company Play It Smart?

## introduction 
This is a case study about the **Bellabeat**, in this case, I will be answered the question by following the steps of **the data analysis process: ask, prepare, process, analyze, share, and act**.

### About the Company
**Urška Sršen** and **Sando Mur** founded **Bellabeat**, a high-tech company that manufactures health-focused smart products.
**Sršen** used her background as an artist to develop beautifully designed technology that informs and inspires women around
the world. Collecting data on activity, sleep, stress, and reproductive health has allowed **Bellabeat** to empower women with
knowledge about their own health and habits. Since it was founded in 2013, **Bellabeat** has grown rapidly and quickly
positioned itself as a tech-driven wellness company for women.

### Stakeholders:

- > **Urška Sršen**: Bellabeat’s co-founder and Chief Creative Officer.


- > **Sando Mur**: Mathematician and Bellabeat’s cofounder; key member of the Bellabeat executive team.

- >**Bellabeat marketing analytics team** : A team of data analysts responsible for collecting, analyzing, and reporting data that helps guide Bellabeat’s marketing strategy. You joined this team six months ago and have been busy learning about Bellabeat’s mission and business goals — as well as how you, as a junior data analyst, can help Bellabeat achieve them.

### Products
- > **Bellabeat app**: The Bellabeat app provides users with health data related to their activity, sleep, stress,
menstrual cycle, and mindfulness habits. This data can help users better understand their current habits and
make healthy decisions. The Bellabeat app connects to their line of smart wellness products.
- > **Leaf**: Bellabeat’s classic wellness tracker can be worn as a bracelet, necklace, or clip. The Leaf tracker connects
to the Bellabeat app to track activity, sleep, and stress.
- > **Time**: This wellness watch combines the timeless look of a classic timepiece with smart technology to track user
activity, sleep, and stress. The Time watch connects to the Bellabeat app to provide you with insights into your
daily wellness.
- > **Spring**: This is a water bottle that tracks daily water intake using smart technology to ensure that you are
appropriately hydrated throughout the day. The Spring bottle connects to the Bellabeat app to track your
hydration levels.

### Deliverables:
- > A clear summary of the business task
- > A description of all data sources used
- > Documentation of any cleaning or manipulation of data
- > A summary of your analysis
- > Supporting visualizations and key findings
- > Your top high-level content recommendations based on your analysis.

### Business task:
Analyze one product of smart device data to gain insight into how consumers are using their smart devices. The insights that will be discovered will then help guide the marketing strategy for the company. 

### Definition of terms:

#### Calories: Calories are units of energy that a food or drink provides.
#### METs(metabolism):

A MET is a ratio of your working metabolic rate relative to your resting metabolic rate. 
Metabolic rate is the rate of energy expended per unit of time. 
It’s one way to describe the intensity of an exercise or activity.
One MET is the energy you spend sitting at rest — your resting or basal metabolic rate. 
So, an activity with a MET value of 4 means you’re exerting four times the energy than you would if you were sitting still.
https://www.healthline.com/health/what-are-mets#definition.

#### Intensities:
Exercise intensity refers to how hard your body is working during physical activity. 
Your health and fitness goals, as well as your current level of fitness, will determine your ideal exercise intensity.
https://www.betterhealth.vic.gov.au/health/healthyliving/exercise-intensity

#### Sedentary
A sedentary lifestyle is one that involves very little or no physical exercise, 
wherein most of the day is spent sitting, lying down, and expending very little energy. 

#### BMI:
Body Mass Index (BMI) is a person’s weight in kilograms (or pounds) divided by the square of height in meters (or feet). 
A high BMI can indicate high body fatness. BMI screens 
for weight categories that may lead to health problems, but it does not diagnose the body fatness or health of an individual.

#### Heart rate:
In medicine, the number of times the heart beats within a certain time period, usually a minute. 
The heart rate can be felt at the wrist, side of the neck, back of the knees, top of the foot, groin,
and other places in the body where an artery is close to the skin. 

#### SleepQuality: https://www.healthline.com/health/healthy-sleep#how-much-sleep-do-you-need?
we have not about the age of the participants so we assume that the age is from 18 to 64



## STEP ONE: **ASK**
**Sršen** asks you to analyze smart device usage data in order to gain insight into 
how consumers use non-Bellabeat smart devices. through a guided question, and these questions are 

**1. What are some trends in smart device usage?**

**2. How could these trends apply to Bellabeat customers?**

**3. How could these trends help influence Bellabeat marketing strategy?**

## STEP TWO: PREPARE

### 1. the dataset
the dataset was generated through a survey, via Amazon Mechanical Turk between 03.12.2016-05.12.2016.
Only 30 users eligibly submitted personal tracker data.
data include daily and hourly physical activity, also sleeps tracking, 
metabolic ratio, and lastly heart rating value.
unfortunately, the data isn't ROCCC (Reliable, Organize, Comprehensive, Current, Cited),
because data is outdated and not current.

### 2. How data are organized
The data  are organized into 18 files in CSV format, more details in following below:

- > dailyActivity_merged: contain all daily physical activity from id, total steps to calories burned 
    (941 rows and 15 columns)

- > dailyCalories_merged: contain the Id,  ActivityDay, and Calories.
    (941 rows and 3 columns)

- > dailyIntensities_merged: contain the Id, Activity, SedentaryMinutes, LightActiveMinutes, FairlyActiveMinutes,         
    VeryactiveMinutes, SedentaryActiveDistance, LightActiveDistance, ModeratelyActiveDistance, VeryActiveDistance.
    (941 rows and 10 columns)
    
- > dailySteps_merged: contain the Id,  ActivityDay, and StepTotal.
   (941 rows and  3 columns)

- > heartrate_second_merged: contain Id, Time,  Value
    (2,483,658 rows and 3 columns)

- > hourlyCalories_merged: contain Id, ActivityHour, Calories
    (22,099 rows and 3 columns)

- > hourlyintensities_merged: contain Id, ActivityHour, TotalIntensity, AverageIntensity
    (22,099 rows and 4 columns)

- > hourlySteps_merged: contain Id, ActivityHour, StepTotal
    (22,099 rows and 3 columns)

- > minutesCaloriesNarrow_merged: Id, ActivityMinutes, Calories
   (1,325,580 rows and 3 columns)

- > minutesCaloriesWide_merged: Id, ActivityMinutes, Calories00, Calories01 ..., Calories59
   (21,645 rows and 62 columns)

- > minutesIntensitiesNarrow_merged: Id, ActivityMinute, Intensity
    (1,325,580 rows and  3 columns)

- > minuteIntensitiesWide_merged: Id, ActivityHour, Intensity00, Intensity01, ..., Intensity59.
    (21,645 rows and  62 columns)

- > minuteMETsNarrow_merged: Id, ActivityHour, METs.
    (1,325,580, 3)
    
- > minuteSleep_merged: Id, date, value, logId.
    (188521 rows and  4 columns)

- > minuteStepsNarrow_merged: Id, ActivityMinute, Steps.
    (1325580 rows and 3 columns)

- > minuteStepsWide_merged: Id, ActivityMinute, Steps00, Steps01, ..., Steps59.
    (21645 rows and 62 columns)

- > sleepDay_merged: Id, SleepDay,  TotalSleepRecords, TotalMinutesAsleep, TotalTimeInBed.
    (413 rows and  5 columns)

- > weightLogInfo_merged: Id, Date, weightKg, weightPounds, Fat, BMI, IsManualReport, LogId.
   (67 rows and  8 columns)
   
### 3.  A word about the dataset 
-The dailyCalories_merged, dailyIntensities_merged, and dailySteps_merged, 
they are just redundant from dailyActivity_merge.

-minutesCaloriesNarrow_merged, minutesCaloriesWide_merged,
minutesIntensitiesNarrow_merged, minutesIntensitiesWide_merged, minuteSleep_merged,
minuteStepsNarrow_merged, minuteStepsWide_merged,are not mature 
(need large time, such as hour, or day )

## STEP THREE: PROCESSING 
### 1. install and load the required library 

1. tidyverse: a core system of packages for data manipulation, visualization, and other things. To see
more visit the following link https://www.tidyverse.org/

2. dplyr: is a library about data manipulation, providing a consistent set of verbs that help you solve the
most common data manipulation challenges. For more info, you can https://dplyr.tidyverse.org/

3. Janitor: is a simple library for cleaning dirty data, you can read more about it in this source, janitor
documentation.

4. skimr: is a comprehensive statistic summary for a data frame, for more skimr

5. ggplot2: is a data visualization library, that visually provides a more flexible show. For more of it check
this link https://ggplot2.tidyverse.org/

6. lubridate: is a date-time library dealing with formats and separators to handle the changing time zone.
See this link https://lubridate.tidyverse.org/

7. corrplot: provides visual correlation between variables, https://cran.r-project.org/web/packages/corrplot/vignettes/corrplot-intro.html

8. ggpubr: is an excellent and flexible package for elegant data visualization in R.
https://rpkgs.datanovia.com/ggpubr/

9. This generic function fits a nonlinear mixed-effects model in the formulation described in Lindstrom and Bates (1990) but allows for nested random effects. The within-group errors are allowed to be correlated and/or have unequal variances.
https://www.rdocumentation.org/packages/nlme/versions/3.1-160/topics/nlme.

```
#install packages
install.packages('tidyverse')
install.packages('dplyr')
install.packages('janitor')
install.packages('skimr')
install.packages('lubridate')
install.packages('ggplot2')

```

```
#library
library(tidyverse)
library(dplyr)
library(janitor)
library(skimr)
library(ggplot2)
library(lubridate)
library(corrplot)
library(ggpubr)
library(nlme)
library(SimDesign)
library(caret)
library(caTools)
library(rmarkdown)

```

### 2. read dataset

read 8 dataset

```
dailyActivity <- read_csv("dataset/dailyActivity_merged.csv")
heartrateSecond <- read_csv("dataset/heartrate_seconds_merged.csv")
hourlyCalories <- read_csv("dataset/hourlyCalories_merged.csv")
hourlyIntensities <- read_csv("dataset/hourlyIntensities_merged.csv")
hourlySteps <- read_csv("dataset/hourlySteps_merged.csv")
mets <- read_csv("dataset/minuteMETsNarrow_merged.csv")
sleepDay <-read_csv("dataset/sleepDay_merged.csv")
weightLogInfo <- read_csv("dataset/weightLogInfo_merged.csv")

```
### 3. summary

-Let's see a summary of each dataset.

```
skim_without_charts(dailyActivity)
skim_without_charts(sleepDay)
skim_without_charts(heartrateSecond)
skim_without_charts(hourlyCalories)
skim_without_charts(hourlyIntensities)
skim_without_charts(hourlyIntensities)
skim_without_charts(mets)
skim_without_charts(weightLogInfo)

```

 In all datasets, as you can see, Columns are more spread than others that's because the columns that have a low standard deviation are clustered around the mean.
In daily activity (dataset01) the TotalDistance and TrackerDistance look the same, also the majority of columns are non-normally distributed, and are skewed to the right, and some of them are flattened.

### 4. Number of Id in each dataset 

- I used the n_distinct() to calculate the number of distinct Id in each dataset. 

```
n_distinct(dailyActivity$Id) 
n_distinct(heartrateSecond$Id)
n_distinct(hourlyCalories$Id)
n_distinct(hourlyIntensities$Id)
n_distinct(hourlySteps$Id)
n_distinct(mets$Id)
n_distinct(sleepDay$Id)
n_distinct(weightLogInfo$Id)

```
- dailyActiviyt (Id): 33

- heartrateSecond (Id): 14

- hourly calorie (Id): 33

- hourlyIntensities (Id): 33

- hourlySteps (Id): 33

- Mets (Id): 33

- sleepDay (Id): 14

- weightLogInfo (Id): 8

### 5.Looking for duplication value 

If there is any duplicated value that will affect the whole analysis.

```
sum(duplicated(dailyActivity))
sum(duplicated(heartrateSecond))
sum(duplicated(hourlyCalories))
sum(duplicated(hourlyIntensities))
sum(duplicated(hourlySteps))
sum(duplicated(mets))
sum(duplicated(sleepDay))
sum(duplicated(weightLogInfo))

```

taken the duplicated() function of all datasets and summing up all  So there are 
3 rows in sleepDay dataset are duplicated, let's remove it

```
sleepDay <- sleepDay %>% 
  distinct()

```
I assigned the sleepDay dataset in the sleepDay variable and distinct all rows, 
let's test again the sleepDay dataset if it is unique or not.

```
sum(duplicated(sleepDay))

```
### 6. Missing value 
after we finish looking for duplicated values than will go to see the missing value.

```
#dailyActivity
sum(is.na(dailyActivity))

#heartrateSecond
sum(is.na(heartrateSecond))

#hourlyCalories
sum(is.na(hourlyCalories))

#hourlyItensities
sum(is.na(hourlyIntensities))

#hourlySteps
sum(is.na(hourlySteps))
#mets
sum(is.na(mets))

#sleepDays
sum(is.na(sleepDay))

#weightsLogInfo
sum(is.na(weightLogInfo))

```
like what we did in duplicated() function when we took the duplicated() function of all datasets and summed up all, we do the same in is.na() function but searching for na value.
so there is 65 na in weightLogInfo, let's go deeper and see which column contains na's.


```
sum(is.na(weightLogInfo$Id))
sum(is.na(weightLogInfo$Date))
sum(is.na(weightLogInfo$WeightKg))
sum(is.na(weightLogInfo$WeightPounds))
sum(is.na(weightLogInfo$Fat)) #65
sum(is.na(weightLogInfo$BMI))
sum(is.na(weightLogInfo$IsManualReport))
sum(is.na(weightLogInfo$LogId))

```
taken the is.na() function for every column in the weightLogInfo then summing up with the sum() function.
So the Fat columns contain 65 missing values, let's fill in this na's
fill(): is a function that helps us to fill the missing value by selecting columns 
[using the next or previous entry,](https://tidyr.tidyverse.org/reference/fill.html)

```
#fill all na by the previous value 
weightLogInfo <- weightLogInfo %>% 
  fill(Fat)
```

assigning the weightLogInfo dataset to weightLogInfo to update this 
the dataset by filling the Fat columns let's check again the na of Fat 

```
sum(is.na(weightLogInfo$Fat)) 

```


### 7. Checking the datatypes

-the datatypes are an essential thing because the analysis wouldn't work properly 
or will lead to bias if there is an error in datatypes.

1. dailyActivity: convert the ActivityDate to be in date and time, by the format of
month, day, and year, and separate to month, day, year, and day of week.

1.1 convert to date and time 

```{r}
#convert AcivityDate to dailyActivity 
dailyActivity <- dailyActivity %>%
  mutate(ActivityDate = (as.Date(ActivityDate, format="%m/%d/%Y")))
```

1.2 separate to month, day, year, and day of week 

```{r}
#create more columns of Month, Day, Year, DayOfWeek
dailyActivity$Day <- format(as.POSIXct(dailyActivity$ActivityDate), format = "%d")
dailyActivity$Month <- format(as.POSIXct(dailyActivity$ActivityDate), format = "%m")
dailyActivity$Year <- format(as.POSIXct(dailyActivity$ActivityDate), format = "%Y")
dailyActivity$DayOfWeek <- format(as.POSIXct(dailyActivity$ActivityDate), format = "%a")
```

-1.3 The structure of daily activity.

```
#convert time in dailyActivity to date and time 

colnames(dailyActivity)
str(dailyActivity)
```

2-heartrateSecond: convert the Time column to be in datetime then separate to day, 
month, year, day of week, hour, minutes seconds

2.1- first convert the Time to DateTime by using the as.POSIXct takes a string and converts it to a date time object by formatting it and using a specific time zone, in this case, the right format is Month/day/year hour:minute: second, and the sys.timezone returns the current time zone, lastly modified and updating it by using mutate

```{r}
heartrateSecond <- heartrateSecond %>% 
  mutate(Time = as.POSIXct(Time, format ="%m/%d/%Y %I:%M:%S %p" , tz=Sys.timezone()))

```

2.2- create more columns from Time, and these columns are, day, month, year, day of the week,
hour, minute, and second

```
#create the day, month, year, hour, minute, second
heartrateSecond$Day <- format(as.POSIXct(heartrateSecond$Time), format = "%d")
heartrateSecond$Month <- format(as.POSIXct(heartrateSecond$Time), format = "%m")
heartrateSecond$Year <- format(as.POSIXct(heartrateSecond$Time), format = "%Y")
heartrateSecond$DayOfWeek <- format(as.POSIXct(heartrateSecond$Time), format = "%a")
heartrateSecond$Hour <- format(as.POSIXct(heartrateSecond$Time), format = "%H")
heartrateSecond$Minute <- format(as.POSIXct(heartrateSecond$Time), format = "%M")
heartrateSecond$Second <- format(as.POSIXct(heartrateSecond$Time), format = "%S")
```

2.3. see the structure of the columns name of heartrateSecond 

```
colnames(heartrateSecond)
str(heartrateSecond)

```

**Note that each dataset that remaining (hourlyCalories,  hourlyIntensities, hourlySteps, mets, sleepDay, and 
weightLogInfo), we will do the same as we did in dailyActivity and heartrateSecond except for some changes we will mention in the right place**

3- hourlyCaloires: convert the ActivityHour to DateTime and separate it into the month, day, year, day of the week, and hour.
    
3.1- convert the ActivityHour to DateTime.

```
#convert the hourlyCalories to DateTime
hourlyCalories <- hourlyCalories %>% 
  mutate(ActivityHour = as.POSIXct(ActivityHour, format ="%m/%d/%Y %I:%M:%S %p" , tz=Sys.timezone()))

```

3.2- separate the month, day, year, day of week, and hour.

```
#separate the Month, Day, Year, Hour, Month, Second, and Day of the week
hourlyCalories$Month <- format(as.POSIXct(hourlyCalories$ActivityHour), format = "%m")
hourlyCalories$Day <- format(as.POSIXct(hourlyCalories$ActivityHour), format = "%d")
hourlyCalories$Year <- format(as.POSIXct(hourlyCalories$ActivityHour), format = "%Y")
hourlyCalories$DayOfWeek <- format(as.POSIXct(hourlyCalories$ActivityHour), format = "%a")
hourlyCalories$Hour <- format(as.POSIXct(hourlyCalories$ActivityHour), format = "%I")

```

3.3 the structure and the column names 

```
colnames(hourlyCalories)
str(hourlyCalories)

```

4. hourlyIntensities: convert the ActivityHour to DateTime and separates it into the month, day, year, day of the week, and hour.
    
4.1- convert the ActivityHour to DateTime.

```{r}
hourlyIntensities <- hourlyIntensities %>% 
  mutate(ActivityHour = as.POSIXct(ActivityHour, format ="%m/%d/%Y %I:%M:%S %p" , tz=Sys.timezone()))

```

4.2- separate the ActivityHour into the month, day, year, and hour
```
#separate the Month, Day, Year, Hour, Month, Second, and Day of the week
hourlyIntensities$Month <- format(as.POSIXct(hourlyIntensities$ActivityHour), format = "%m")
hourlyIntensities$Day <- format(as.POSIXct(hourlyIntensities$ActivityHour), format = "%d")
hourlyIntensities$Year <- format(as.POSIXct(hourlyIntensities$ActivityHour), format = "%Y")
hourlyIntensities$DayOfWeek <- format(as.POSIXct(hourlyIntensities$ActivityHour), format = "%a")
hourlyIntensities$Hour <- format(as.POSIXct(hourlyIntensities$ActivityHour), format = "%I")

```

4.3- Structure and column names of hourlyIntensities.

```
str(hourlyIntensities)
colnames(hourlyIntensities)
```

5- hourlySteps: **same as  the hourlyCalories and hourlyIntensities**

5.1
```
#convert to ActivityHour in hourly steps to be DateTime
hourlySteps <- hourlySteps %>% 
  mutate(ActivityHour = as.POSIXct(ActivityHour, format ="%m/%d/%Y %I:%M:%S %p" , tz=Sys.timezone()))

```


5.2
```{r}
#separate the Month, Day, Year, Hour, Month, Second, and Day of the week
hourlySteps$Month <- format(as.POSIXct(hourlySteps$ActivityHour), format = "%m")
hourlySteps$Day <- format(as.POSIXct(hourlySteps$ActivityHour), format = "%d")
hourlySteps$Year <- format(as.POSIXct(hourlySteps$ActivityHour), format = "%Y")
hourlySteps$DayOfWeek <- format(as.POSIXct(hourlySteps$ActivityHour), format = "%a")
hourlySteps$Hour <- format(as.POSIXct(hourlySteps$ActivityHour), format = "%I")
```

5.3:  structure and colnames of hourlySteps.

```
#convert ActivityHour in houlrySteps
colnames(hourlySteps)
str(hourlySteps)

```
6: mets: convert the ActivityMinute to  datetime then separate it to month, day, year, hour, minute, second  %p for pm and am 

6.1: convert to ActivityMinute to datetime 
```{r}
#ActivityMinute 
mets <-  mets %>% 
  mutate(ActivityMinute = as.POSIXct(ActivityMinute, format ="%m/%d/%Y %I:%M:%S %p" , tz=Sys.timezone()))
```

6.2: convert the datetime to month,  day, year, hour, minute, second and %p
```{r}
#create the day, month, year, hour, minute, second
mets$Day <- format(as.POSIXct(mets$ActivityMinute), format = "%d")
mets$Month <- format(as.POSIXct(mets$ActivityMinute), format = "%m")
mets$Year <- format(as.POSIXct(mets$ActivityMinute), format = "%Y")
mets$DayOfWeek <- format(as.POSIXct(mets$ActivityMinute), format = "%a")
mets$Hour <- format(as.POSIXct(mets$ActivityMinute), format = "%H")
mets$Minute <- format(as.POSIXct(mets$ActivityMinute), format = "%M")
mets$Second <- format(as.POSIXct(mets$ActivityMinute), format = "%S")

```

6.3: structure and column names of mets.

```
colnames(mets)
str(mets)  

```
7: sleepDay: convert the SleepDay to DateTime and separating it into month, day, and year

7.1:SleepDay convert to DateTime 
```{r}
#create the ActivityDate
sleepDay <- sleepDay %>% 
  mutate(ActivityDate = as.Date(SleepDay, format ="%m/%d/%Y"))
```

7.2:convert to month, day, and year

```
#create the day, month, year, hour, minute, second
sleepDay$Day <- format(as.POSIXct(sleepDay$ActivityDate), format = "%d")
sleepDay$Month <- format(as.POSIXct(sleepDay$ActivityDate), format = "%m")
sleepDay$Year <- format(as.POSIXct(sleepDay$ActivityDate), format = "%Y")
sleepDay$DayOfWeek <- format(as.POSIXct(sleepDay$ActivityDate), format = "%a")
```

7.3: structure and colnames.

```
#convert SleepDay to date &&  rename it as AcivityDate 
colnames(sleepDay)
str(sleepDay)  

```

8: weightLogInfo: convert the date to DateTime,  named ActivityDate, and separate it to 

8.1: convert to DateTime.

```
#convert the date to DateTime and named ActivityDate
weightLogInfo <- weightLogInfo %>% 
  mutate(ActivityDate = as.POSIXct(Date, format ="%m/%d/%Y %I:%M:%S %p" , tz=Sys.timezone()))

```

8.2: separate into Day, Month, year, dayOfWeek, Hour, minute, and second. 

```
#creates columns Day, Month, Year, DayOfWeek, Hour, Minute, Second
weightLogInfo$Day <- format(as.POSIXct(weightLogInfo$ActivityDate), format = "%d")
weightLogInfo$Month <- format(as.POSIXct(weightLogInfo$ActivityDate), format = "%m")
weightLogInfo$Year <- format(as.POSIXct(weightLogInfo$ActivityDate), format = "%Y")
weightLogInfo$DayOfWeek <- format(as.POSIXct(weightLogInfo$ActivityDate), format = "%a")
weightLogInfo$Hour <- format(as.POSIXct(weightLogInfo$ActivityDate), format = "%I")
weightLogInfo$Minute <- format(as.POSIXct(weightLogInfo$ActivityDate), format = "%M")
weightLogInfo$Second <- format(as.POSIXct(weightLogInfo$ActivityDate), format = "%S")
```

8.3: structure and colnames of weightLogInfo.

```
#convert Date to datetime && rename it ActivityDate && add more column 
colnames(weightLogInfo)
str(weightLogInfo)

```

8.4: remove the Date column from weightLogInfo.

```
#remove the weightLogInfo$Date
weightLogInfo <- weightLogInfo[-2]

```

###7. Join the datasets
joining is a useful tool when you want to combine two datasets together.

1. Joining the hourlyCalories, hourlyIntensities, hourlySteps.

```
#so lets merge the hourlyCalories, hourlyIntensities, and hourlySteps
colnames(hourlyCalories)
colnames(hourlyIntensities)
colnames(hourlySteps)

```
1.2: let's begin by combining the hourlyCalories and hourlyIntensities by Id, ActivityHour, Month, Year, DayOfWeek, Hour.

```
#merge the hourlyCalories and hourlyIntensities
hour <- inner_join(hourlyCalories, hourlyIntensities, 
                   by=c("Id", "ActivityHour", "Day", "Month", "Year", "DayOfWeek", "Hour"))
```

1.3: combining the hour and hourlySteps by Id, ActivityHour, Month, Year, DayOfWeek, Hour.

```
#merge the hour with hourlySteps
HourlyActivity <- inner_join(hour, hourlySteps, by=c("Id", "ActivityHour", "Day", "Month", "Year", "DayOfWeek", "Hour"))

#head
head(HourlyActivity)

#colnames
colnames(HourlyActivity)

```
- using inner_join(): return rows if data lives in both tables.
we use the inner_join to return data in all three datasets.

-2. Combine the heartrate and mets:
take the dimension heartrateSecond and mets

```
#dimension heartrateSecond and mets
dim(heartrateSecond)
dim(mets)

```

- columns heartrateSecond and mets.

```{r}
colnames(heartrateSecond)
colnames(mets)
```

- Before jumping to join the mets and heartrateSecond, we need to do things such as first of all, renaming the ActivityMinute to Time to be consistent with Time in heartrateSecond, then creating an average of value in terms of the hour in heartraterateSecond, then reorder the heartrate columns **Id, Time, Day, Month, DayOfWeek,  Year, Hour,  Value, meanValue** ,
then Create an average of METs in terms of Hour, then reorder to **Id, Time, Day, Month, DayOfWeek, Year, Hour, Value, meanValue**, then join the heartrate and mets.

 - > renaming the ActivityMinute to Time.
 
```
mets <- mets %>% 
  rename(Time = ActivityMinute)

```
 
- > create an average value in terms of hours in heartrate rate.

```{r}
heartrate <- heartrateSecond %>% 
  group_by(Hour) %>% 
  summarise(meanValue = mean(Value), Value,
            Time, Id, Day, Month, Year, DayOfWeek)
```

- > create average of value in terms of hour in heartraterate

```{r}
heartrate <- heartrateSecond %>% 
  group_by(Hour) %>% 
  summarise(meanValue = mean(Value), Value,
            Time, Id, Day, Month, Year, DayOfWeek)

```

- > reorder the hearterate dataset columns.

```{r}
heartrate <- heartrate[,c("Id", "Time", "Day", "Month", "DayOfWeek", "Year", "Hour",
                          "Value", "meanValue")]
```

- > Create average of METs in terms of Hour:

```{r}
Mets <- mets %>% 
  group_by(Hour) %>% 
  summarise(meanMETs = mean(METs), Id,  METs,
            Time, Month, Year, Day, DayOfWeek)

```

- > reorder the columnsof Mets 

```{r}
Mets <-Mets[, c("Id", "Time", "Day", "Month", "Year", "DayOfWeek", "Hour", "METs", "meanMETs")]

```

- > merge the Mets and heartrate

```{r}
MetsHeartrate <- inner_join(Mets, heartrate, by=c("Id", "Time", "Day", "Month", "Year", "DayOfWeek", "Hour"))

```

3. Combine the dailyActivity, sleepDay, and weighLogInfo.

-First, we will remove the TrackerDistance from dailyActivity, because it is the same as TotalDistance, then still dailyActivity, create a category column called typeOfActivity, and create a column called average steps from TotalSteps, then create two new columns in sleepDay, one is TotalSteps in Hour by taken the TotalMinutesAsleep and divided by 60 and other by creating category column called SleepQuality, then in weightLogInfo create the BMI result by drove a category from result,
reorder the sleepDay, the weightLogInfo  and dailyActivity, and lastly join the sleepDay and dailyActivity. 

3.1- remove the TrackerDistance:

```{r}
dailyActivity <- dailyActivity[-5]

```

3.1- Create a category column called typeOfActivity (AverageSteps, typeOfActivity):

```{r}
dailyActivity <- dailyActivity %>% 
  group_by(Id, TotalSteps) %>% 
  mutate(AverageSteps = mean(TotalSteps)) %>% 
  mutate(typeOfActivity = case_when(AverageSteps < 5000 ~ "Sedentary",
                                  AverageSteps >= 5000 & AverageSteps < 7500 ~ "ModeratelyActive",
                                  AverageSteps >= 7500 & AverageSteps < 10000 ~ "FairlyActive",
                                  AverageSteps >= 10000 & AverageSteps < 12500 ~ "VeryActive", 
                                  AverageSteps >= 12500 ~ "HighlyActive"))

```

3.2- create new columns in sleepDay (TotalHourAsleep, SleepQuality).

```{r}
sleepDay <- sleepDay %>% 
  mutate(TotalHourAsleep = TotalMinutesAsleep/60,
         SleepQuality = case_when(TotalHourAsleep < 7 ~ "Poor-Sleep",
                                 TotalHourAsleep >=7 & TotalHourAsleep < 9 ~ "Well-Sleep",
                                 TotalHourAsleep >= 9 ~ "Over-Sleep"))

```

3.3- create a BmiResult in weightLogInfo.

```{r}
weightLogInfo <- weightLogInfo %>% 
  mutate(BmiReslut = case_when(BMI < 18.5 ~ "Under-weight",
                               BMI >= 18.5 & BMI < 25 ~ "Normal-weight",
                               BMI >= 25 & BMI < 30 ~ "Over-weight",
                               BMI >= 30 & BMI < 35 ~ "Obese(class I)",
                               BMI >= 35 & BMI < 40 ~ "Obese(class II)",
                               BMI >= 40 ~ "Obese(class III)" ))

```

3.4- reorder sleepDay columns 

```{r}

sleepDay <- sleepDay[,c("Id", "ActivityDate", "Day", "Month", "Year", "DayOfWeek", "TotalSleepRecords",
                        "TotalMinutesAsleep", "TotalTimeInBed", "TotalHourAsleep", "SleepQuality")]
```

3.5- reoder weightLogInfo columns.

```{r}
weightLogInfo <- weightLogInfo[,c("Id", "ActivityDate", "Day", "Month", "Year", "DayOfWeek", 
                                  "Hour", "Minute", "Second", "WeightKg", "WeightPounds",
                                  "Fat", "BMI", "IsManualReport", "LogId", "BmiReslut")]
```


3.6 reoder the dailyActivity columns.

```{r}

dailyActivity <- dailyActivity[, c("Id", "ActivityDate", "Day", "Month", "Year", "DayOfWeek",
                                   "TotalSteps", "TotalDistance", "LoggedActivitiesDistance", 
                                   "VeryActiveDistance", "ModeratelyActiveDistance", "SedentaryActiveDistance",
                                   "VeryActiveMinutes", "FairlyActiveMinutes",
                                   "LightlyActiveMinutes", "SedentaryMinutes", "Calories", "AverageSteps",
                                   "typeOfActivity")]
```

3.7- merge the dailyActivity and sleepDay in DailyActivity by left_join (): that return columns from dailyActivity and machted columns from the eight sleep

```
sleepDay <- sleepDay[-5]
DailyActivity <- left_join(dailyActivity, sleepDay, 
                           by = c("Id", "ActivityDate", "Day", "Month", "DayOfWeek"))

```

Looks like there is a missing value, let's see which columns contain missing values and handling by filling in all missing values.

```
sum(is.na(DailyActivity$Id))
sum(is.na(DailyActivity$ActivityDate))
sum(is.na(DailyActivity$TotalSteps))
sum(is.na(DailyActivity$TotalDistance))
sum(is.na(DailyActivity$LoggedActivitiesDistance))
sum(is.na(DailyActivity$VeryActiveDistance))
sum(is.na(DailyActivity$ModeratelyActiveDistance))
sum(is.na(DailyActivity$LightActiveDistance))
sum(is.na(DailyActivity$SedentaryActiveDistance))
sum(is.na(DailyActivity$VeryActiveMinutes))
sum(is.na(DailyActivity$FairlyActiveMinutes))
sum(is.na(DailyActivity$LightlyActiveMinutes))
sum(is.na(DailyActivity$SedentaryMinutes))
sum(is.na(DailyActivity$Calories))
sum(is.na(DailyActivity$Day))
sum(is.na(DailyActivity$Month))
sum(is.na(DailyActivity$Year))
sum(is.na(DailyActivity$DayOfWeek))
sum(is.na(DailyActivity$TotalSleepRecords)) #530
sum(is.na(DailyActivity$TotalMinutesAsleep)) #530 
sum(is.na(DailyActivity$TotalTimeInBed)) #530
sum(is.na(DailyActivity$TotalHourAsleep)) #530
sum(is.na(DailyActivity$SleepQuality)) #530

```
- the columns that contain the missing value are, TotalSleepRecords, TotalMinuteAsleep, 
TotalTimeInBed, TotalHourAsleep, SleepQuality.

let's deal with them one by one. In order to do that we must check for datatypes because it helps to deal with missing value

```
typeof(DailyActivity$TotalSleepRecords)
typeof(DailyActivity$TotalMinutesAsleep)
typeof(DailyActivity$TotalHourAsleep)
typeof(DailyActivity$TotalTimeInBed)


#fill  the TotalMinutesASleep, TotalHourASleep and TotalTimeInBed
DailyActivity$TotalMinutesAsleep[is.na(DailyActivity$TotalMinutesAsleep)] <- mean(DailyActivity$TotalHourAsleep, na.rm = TRUE)
DailyActivity$TotalHourAsleep[is.na(DailyActivity$TotalHourAsleep)] <- mean(DailyActivity$TotalHourAsleep, na.rm = TRUE)
DailyActivity$TotalTimeInBed[is.na(DailyActivity$TotalTimeInBed)] <- mean(DailyActivity$TotalTimeInBed, na.rm = TRUE)

```

Let's check again if there's a na in those columns.

```
sum(is.na(DailyActivity$TotalSleepRecords)) 
sum(is.na(DailyActivity$TotalMinutesAsleep))  
sum(is.na(DailyActivity$TotalTimeInBed)) 
sum(is.na(DailyActivity$TotalHourAsleep)) 
sum(is.na(DailyActivity$SleepQuality)) 

```

 still missing value in the TotalSleepRecords and the SleepQuality we can remove na's during the analysis step.

**now let's go to the analysis step**

## STEP THREE: ANALYSIS

### 1. take the head and, colnames in all 4 new dataset datasets.

1. head()

```
head(DailyActivity)
head(HourlyActivity)
head(MetsHeartrate)
head(weightLogInfo)

```
2. colnames()

```

colnames(DailyActivity)
colnames(HourlyActivity)
colnames(MetsHeartrate)
colnames(weightLogInfo)

```

### 2. DailyActivity: 
- 
let's see how many Steps each Id is, but first, we need to create another version of the Id that has a character datatype because the default datatype of the Id is not satisfied.

```
DailyActivity$charId <- as.character(DailyActivity$Id)

```

Visual of TotalSteps each Id.

```
ggplot(DailyActivity, aes(x = charId, y = TotalSteps, fill = charId))+
    geom_bar(stat = "identity") + theme(axis.text.x = element_text(angle = 90))+
    scale_y_continuous(n.breaks = 10)+
    labs(title = "The Daily TotalSteps of each Id", x = "Id", y = "TotalSteps")

```

The chart above shows the total steps of each Id, some IDs reach higher than 300000 steps while a few others didn't exceed 100000 steps. 
I assumed that the first ones who reach more than 300000 steps they are may be working in a job that takes a lot of walking, having enough time to walk, or doing exercise on a treadmill, conversely speaking goes those who didn't exceed the 100000 steps.
let's see the daily Calories that are burned by each id.

```
#Calories for each id 
ggplot(DailyActivity, aes(x = charId, y = Calories, fill = charId))+
  geom_bar(stat = "identity") + theme(axis.text.x = element_text(angle = 90))+
  scale_y_continuous(n.breaks = 10)+
  labs(title = "The Daily Calories of each Id", x = "Id", y = "Calories")

```

we can see the correlation between the Total steps and Calories more later in this analysis, but if we compared the chart of TotalSteps and Id with that above, they look similar except for a significant proportion of the population exceed, we interpreted that may be for instance they burning their calories in the gym, let's see what we can find when we input the type of Activity.

```{r}
ggplot(DailyActivity, aes(x = charId, y = TotalSteps, fill = typeOfActivity))+
  geom_bar(stat = "identity") + theme(axis.text.x = element_text(angle = 90))+
  scale_y_continuous(n.breaks = 10)+
  labs(title = "The total steps in terms type of activity of all id ", x = "Id", y = "TotalSteps")
```

the chart shows that participants who are sedentary are less active, and those who walk a lot are highly active.
and the chart also shows the participants who exceed the 300000 or near to it, the great portion of their activity are HighlyActive.
let's are the Calories with the type of activity of each Id. 

```{r}
#Calories for each Id in terms of type of activity 
ggplot(DailyActivity, aes(x = charId, y = Calories, fill = typeOfActivity))+
  geom_bar(stat = "identity") + theme(axis.text.x = element_text(angle = 90))+
  scale_y_continuous(n.breaks = 10)+
  labs(title = "The Daily Calories of each Id in terms of Type of Activity", x = "Id", y = "Calories")
```

- This above chart is similar to the chart above it, the participants that have burning calories are very or highly active, but there are some Id burning calories without walking by at the gym or something unusual.
 how about the sleep quality? how the steps can affect the sleep quality of each Id?

``
#sleepQuality and Total steps of Id 
DailyActivity %>% 
  group_by(charId, SleepQuality, TotalSteps) %>% 
  summarise(SleepQualityNA = na.omit(SleepQuality)) %>% 
  ggplot(aes(x =  charId, y = TotalSteps, fill = SleepQualityNA))+
  geom_bar(stat = "identity", position = "dodge")  + theme(axis.text.x = element_text(angle = 90))+
  scale_y_continuous(n.breaks = 10)+
  labs(title = "Total Sleep of al Id in terms of Sleep Quality ",  x = "Id", y = "Total Sleeps", 
      )

```
the chart shows that participants who walk a lot they sleeping well or sleeping poorly.
a few participants they one category of sleep and it is poor sleep or oversleeping
the probability distribution of total steps.

```{r}

ggplot(DailyActivity, aes(x = TotalSteps)) + 
geom_density(fill="#69b3a1") + 
  scale_y_continuous(n.breaks = 5)+
  scale_x_continuous(n.breaks = 15)+
  geom_vline(xintercept = mean(DailyActivity$TotalSteps), color= 'red')+
  geom_vline(xintercept = median(DailyActivity$TotalSteps), color="blue")+
   labs(title = "The Probability Distribution of Steps ",  x = "Steps", y = "Denstiy Probability", 
      )

```
- the majority of the steps lay this area from 5000 to 12500
- the median and mean are near to each other but we can't call it normally distributes

create a function to calculate the mode
the probability distribution of Calories.

```{r}
mode <- function(x){
   var <- unique(x)
   var[which.max(tabulate(match(x, var)))]

}

ggplot(DailyActivity, aes(x = Calories)) + 
geom_density(fill="#69b3a1") + 
  scale_y_continuous(n.breaks = 5)+
  scale_x_continuous(n.breaks = 10)+
  geom_vline(xintercept = mode(DailyActivity$Calories))+
  geom_vline(xintercept = mean(DailyActivity$Calories), color="red")+
   labs(title = "The Probability Distribution of Calories ",  x = "Calories", y = "Denstiy Probability", 
      )
```
the chart shows the calories have one pike or mode in 2000 and mean
the majority of calories between 1500 and 3000
let's see the probability distribution for the total steps of each type of activity.


```{r}

ggplot(DailyActivity, aes(x = TotalSteps,  group = typeOfActivity, fill = typeOfActivity)) + 
geom_density(adjust=1.5, alpha=.4) + 
  scale_y_continuous(n.breaks = 15)+
  scale_x_continuous(n.breaks = 10)+
   labs(title = "The Probability Distribution of Steps ",  x = "Steps", y = "Denstiy Probability", 
      )
```

this chart shows the distribution of each activity category over the Total Steps,
the distribution of HighlyActive is tailed to the right it can be because of outliers.

```

ggplot(DailyActivity, aes(x = Calories,  group = typeOfActivity, fill = typeOfActivity)) + 
geom_density(adjust=1.5, alpha=.4) + 
  scale_y_continuous(n.breaks = 15)+
  scale_x_continuous(n.breaks = 10)+
   labs(title = "The Probability Distribution of Steps ",  x = "Calories", y = "Denstiy Probability", 
      )

```
in the chart above the probability distribution of Calories for each type of Activity, all activities are focused on the area from 1500 to 3000


```

#the boxpot of typeOfActivity and TotalSteps 
ggplot(DailyActivity, aes(TotalSteps, typeOfActivity, fill = typeOfActivity))+
  geom_boxplot()+
  theme(
    legend.position="none",
    plot.title = element_text(size=11)
  ) +
  scale_x_continuous(n.breaks = 10)+
  ggtitle("Total steps of each activity type") +
  xlab("Total Steps") + 
  ylab("Type of Activity")


```

The range of data is different from one to another.
And there is some outliers point in highly Active.
the majority of the data does not exceed 12500.
the 25%  of data looks like same 
let's see what the box plot of the Calories and type of activity tell us

```
#Boxplot 
ggplot(DailyActivity, aes(Calories, typeOfActivity, fill = typeOfActivity))+
  geom_boxplot()+ 
  theme(legend.position="none",
    plot.title = element_text(size=11)) +
  ggtitle("the calories burend pf each activit type") +
  xlab("Type of activity") + 
  ylab("Calories")
```

the chart above shows the sedentary has a lot of outliers and is skewed to the left.
very active also have outlier but look like normally distributed.
let's do more of a box plot comparing the sleep quality.

```

DailyActivity %>% 
  group_by(SleepQuality, TotalSteps) %>% 
  summarise(SleepQualityNA = na.omit(SleepQuality)) %>% 
  ggplot(aes(TotalSteps, SleepQualityNA, fill = SleepQualityNA)) +
  geom_boxplot()+ 
  theme(legend.position="none",
        plot.title = element_text(size=11)) +
  ggtitle("The TotalSteps of each sleep quality ") +
  xlab("TotalSteps") + 
  ylab("TType of Activity")
  
```

the wellsleep skewed to the left meaning that the majority of data recorded on the right of the data and also have some outliers.
the sleep is right skewed means that more than half of the data are laid on left.
So let's see the calories of each sleep category.

```

#Boxplot for sleepQuality and  Calories
DailyActivity %>% 
  group_by(Calories, SleepQuality) %>% 
  summarise(SleepQualityNA = na.omit(SleepQuality)) %>% 
  ggplot(aes(Calories, SleepQualityNA, fill = SleepQualityNA)) +
  geom_boxplot()  +
  ggtitle("The TotalSteps of each sleep quality ") +
  xlab("Type of Activity") + 
  ylab("Calories")

```
let's use the density probability distribution to show how each sleep category is distributed over the calories.

```
DailyActivity %>% 
  group_by(Calories, SleepQuality) %>% 
  summarise(SleepQualityNA = na.omit(SleepQuality)) %>%
  ggplot(aes(x = Calories,  group = SleepQualityNA, fill = SleepQualityNA)) + 
  geom_density(adjust=1.5, alpha=.4) + 
    scale_y_continuous(n.breaks = 15)+
    scale_x_continuous(n.breaks = 10)+
    labs(title = "The Probability Distribution of Steps ",  x = "Calories", y = "Denstiy Probability", 
      )

```

this chart above and others above it, shows how each category of sleep quality is distributed over the calories all data  are laid on 1500 and 3500 calories and the majority of Calory in the poor sleep category is between 0%-25% or between 75%-100%

### 3. HourlyActivity : 

the Calories of each Id by the hour.

```

#calories in an hour 
HourlyActivity %>% 
  group_by(Hour, Calories, Id) %>% 
  summarise(charId = as.character(Id)) %>% 
  ggplot(aes(Hour, Calories, group = charId,  fill = charId, color=charId))+ 
  geom_bar(stat = "identity", position = "dodge") + theme(axis.text.x = element_text(angle = 90))+
  labs(title = "Calories per hour for each Id")

```
the majority of Id didn't reach 500 calories by an hour of the day.
let's compare that with the next chart.

```
HourlyActivity %>% 
  group_by(Hour, StepTotal, Id) %>% 
  summarise(charId = as.character(Id)) %>% 
  ggplot(aes(Hour, StepTotal, group = charId,  fill = charId, color=charId))+ 
  geom_bar(stat = "identity", position = "dodge") + theme(axis.text.x = element_text(angle = 90))+
  labs(title = " Steps in Total per hour for each Id")

```
the chart above is about the total step of each Id by the hour.
the Id that has the highest total steps also has the highest calory burned.

### 4. Linear trends: 
#### 4.1. linear trends of Calories and  TotalSteps:

```

ggplot(DailyActivity, aes(TotalSteps, Calories,))+
  geom_point()+  theme(axis.text.x = element_text(angle = 45)) + 
  scale_y_continuous(n.breaks = 20)+
  scale_x_continuous(n.breaks = 20)+
  geom_smooth()+labs(title="The relationship between Calories and total steps", x="Steps in total", y="Calories")
```

the chart above shows the linear trend between the Total Steps and Calories
the line in the blue show there is a positive relationship between Total steps and Calories.
yet we didn't have a clear view of how much the relationship is in percentage but we can pursue that in later charts.
the majority of the data points from 0 to 20,000 steps.
the data point in [360000, 2750] maybe it's an outlier.

#### 4.2 linear trends of Calories and  TotalSteps in terms of the type of activity :

```{r}
ggplot(DailyActivity, aes(TotalSteps, Calories, fill = typeOfActivity,color = typeOfActivity))+
  geom_point()+
  theme(axis.text.x = element_text(angle = 45)) + 
  scale_y_continuous(n.breaks = 10)+
  scale_x_continuous(n.breaks = 10)+
  geom_smooth() + labs(title="The relationship between Calories and total steps in terms of type of activity", x="Steps in total", y="Calories")

```

- in the chart above each type is somehow well clustered except the HighlyActive and Sedentary.
- the line shows increasing to the point 280000 and decreasing.
- the ModeratelyActive, VeryActive, and FairlyActive takes the pattern.

#### 4.3. linear trends of Caloires and TotalDistance

```

# Linear trend of TotalDistance, Calories by filling  typeOfActivity 
ggplot(DailyActivity, aes(TotalDistance, Calories))+
  geom_point()+
  geom_smooth()+
  theme(axis.text.x = element_text(angle = 45)) + 
  scale_y_continuous(n.breaks = 20)+
  scale_x_continuous(n.breaks = 20)+labs(title="The relationship between the Total Distance and Calories", x = "Total Distance", y="Calories")

```
-the chart above shows the positive relationship between the Total distance and calories.
-the chart looks like the chart that is above of "The relationship between Calories and total step"

#### 4.4. linear trends of Calories and  TotalDistance in terms of the type of activity.

```
ggplot(DailyActivity, aes(TotalDistance, Calories, fill = typeOfActivity,color = typeOfActivity))+
  geom_point()+
  theme(axis.text.x = element_text(angle = 45)) + 
  scale_y_continuous(n.breaks = 10)+
  scale_x_continuous(n.breaks = 10)+
  geom_smooth() + labs(title="The relationship between Calories and total steps in terms of type of activity",      x="TotalDistance", y="Calories")
```
-the chart above shows the positive relationship between the Total distance and calories in terms of the type of Activity.
-the chart looks like the chart that is above of "The relationship between Calories and total Distance"

### 5. correlation between the columns of each dataset 
#### 5.1. correlation between DailyActivity columns.

first, we will remove the unnecessary columns for the correlation, then create a new dataset, and finally, we will do the correlation.

```
#remove the unnecessary columns for the correlation

corDaily <- subset(DailyActivity, select = -c(Id, ActivityDate, Day, Month, Year, DayOfWeek, typeOfActivity,  
                                              TotalSleepRecords,   SleepQuality, charId))

colnames(corDaily)

```

- After we remove all columns that are not double, we can now do the correlation by using the pearson method
-Pearson correlation (r), which measures a linear dependence between two variables (x and y). 
-It’s also known as a parametric correlation test because it depends on the distribution of the data. 
-It can be used only when x and y are from a normal distribution. 

> Pearson equation correlation:
              $r =\frac{\sum\left(x_{i}-\bar{x}\right)\left(y_{i}-\bar{y}\right)}{\sqrt{\sum\left(x_{i}-\bar{x}\right)^{2}    \sum\left(y_{i}-\bar{y}\right)^{2}}}$
              

```
corDaily_core <- cor(corDaily, method = "pearson")

#corplot
corrplot(corDaily_core, method = "square")


```
 
-the plot shows all the correlations between columns there are strong positives between TotalSteps and TotalDistance but isn't
important for us because it measures the same thing in the step, also there is a positive correlation between the TotalSteps or  TotalDistance with AverageSteps. there is some strong negative correlation such as TotalMinuteASleep and SedenataryMinutes.
- let's do the correlation of the whole columns with the Calories columns


> TotalSteps and Calories: 0.59156809

> TotalDistance and Calories: 0.64496187

> LoggedActivitiesDistance and Calories: 0.207595111

> VeryActiveDistance and Calories: 0.49195856

> ModeratelyActiveDistance and Calories: 0.216789872

> SedentaryActiveDistance and Calories: 0.043651875

> VeryActiveMinutes and Calories: 0.615838268

> FairlyActiveMinutes and Calories: 0.29762347

> LightlyActiveMinutes and Calories: 0.2867175

> SedentaryMinutes and Calories: -0.10697305

> AverageSteps and Calories: 0.59156809

> TotalMinutesAsleep and Calories: 0.090155292

> TotalTimeInBed and Caloriers: -0.09395644

> TotalHourAsleep and Calories: -0.02209364

-The TotalSteps, TotalDistance , AverageSteps, and VeryActiveMinutes are the three that have somehow had a slightly strong positive correlation with Calories, but the 
- the four feature range around ~0.6 or ~60%.


#### 5.2 correlation between HourlyActivity columns.

```
colnames(HourlyActivity)

corhourly <- subset(HourlyActivity, select = c(Calories, TotalIntensity, AverageIntensity, StepTotal))

colnames(corhourly)
```

- we will be doing the correlation between corhourly columns by using pearson method.

```

corHourly_cor <- cor(corhourly, method = "pearson")

#corplot
corrplot(corHourly_cor, method = "number")

```

- as you can see in the cor plot above the Calories have a strong correlation with the three.

### 5.3  create a model to predicate the calories in both dailyActivity and HourlyActivity 
before begin creating a model, will let visualize again the correlation between columns then use corr.test to test the correlation,  then create a model based on that test.

1. scatter plot for TotalSteps and Calories.
```{r}
#plot the corr between TotalSteps and Calories
ggscatter(corDaily, x = "TotalSteps", y = "Calories",
                     add = "reg.line", conf.int = TRUE, 
                    cor.coef = TRUE, cor.method = "pearson")
```

2. TotalDistance and Caloris.

```
#plot the corr between TotalDistance and Calories
ggscatter(corDaily, x = "TotalDistance", y = "Calories",
          add = "reg.line", conf.int = TRUE, 
          cor.coef = TRUE, cor.method = "pearson")

```

3. VeryActiveMinutes and Calories.

```
#plot the corr between VeryActiveMinutes and Calories
ggscatter(corDaily, x = "VeryActiveMinutes", y = "Calories",
          add = "reg.line", conf.int = TRUE, 
          cor.coef = TRUE, cor.method = "pearson")

```

4.  Sedentary and calories: can't rely on sedentary to predict the Calories
```{r}
#plot the corr between SedentaryActiveDistance and Calories 
ggscatter(corDaily, x = "SedentaryActiveDistance", y = "Calories",
          add = "reg.line", conf.int = TRUE, 
          cor.coef = TRUE, cor.method = "pearson")
```

in all scatter plots above as you can see, we can't create a model based on one feature say totalDistance, or totalSteps but let's say hourlyActivity then we will return to fix that one.

5. corHourly: StepTotal  vs Calories
```{r}
ggscatter(corhourly, x = "StepTotal", y = "Calories",
          add = "reg.line", conf.int = TRUE, 
          cor.coef = TRUE, cor.method = "pearson")
```
6. AverageIntensity vs Calories.

```
#plot the corr between AverageIntensity and calories
ggscatter(corhourly, x = "AverageIntensity", y = "Calories",
          add = "reg.line", conf.int = TRUE, 
          cor.coef = TRUE, cor.method = "pearson")
```

as Steps or average intensity increase the Calories also increase

#### corr.test to test the features both in DailyActivity and HourlyActivity.

```{r}
#TotalSteps, Calories
cor.test(corDaily$TotalSteps, corDaily$Calories, method = "pearson")

#TotalDistance, Calories
cor.test(corDaily$TotalDistance, corDaily$Calories, method = "pearson")

#VeryActiveMinutes, Calories
cor.test(corDaily$VeryActiveMinutes, corDaily$Calories, method = "pearson")


```
let's interpret all corr.test  of corDaily above.

1- data corDaily:  TotalSteps and Calories:
the p-value is less than 2.2e-16 so the alternative hypothesis is true there is no correlation between the TotalSteps and Calories because we assume there is a correlation between Calories and TotalSteps this a null hypothesis and will be rejected because the p-value is less than the significant level in this case 0.05.

2- data corDaily: TotalDistance and Calories above.
an alternative hypothesis is a true correlation because the p-value is less than  2.2e-16

3- data corDaily: VeryActiveMinutes and Calories
alternative hypothesis is a true correlation because the p-value is less than  2.2e-16

let's test the correlation in hourly activity.

```
#StepTotal, Calories
cor.test(corhourly$StepTotal, corhourly$Calories)

#AverageIntensity and calories
cor.test(corhourly$AverageIntensity, corhourly$Calories)
```

#### CREATE A MODEL IN DAILYACTIVITY
let's create a linear model by using multiple features(TotalSteps, TotalDistance, VeryActiveMinutes)

```
lm_model <- lm(Calories ~ TotalSteps + TotalDistance + VeryActiveMinutes 
               , data= corDaily)
```

resume of lm_model

```
summary(lm_model)

```
let's plot the lm_model and see the violations in the linear regression assumptions.
But the assumptions of the linear regression model are: 
> Linearity of the data: The relationship between features and target needs to be linear.
> Normality of residuals. The residuals are normally distributed.
> Homogeneity or constant variance: the variance of residuals needs to be constant.

```
plot(lm_model, which = 1)

```
-the plot of Fitted value vs Residuals shows linearity is violated because the majority of the points are located in the first quarter 25%, the point 51 maybe is an outlier

```

plot(lm_model, which = 2)

```

the quantile quantile  normal show the features are not normally distributed because the bottom left and top right of the data moves from the line and means that are not normally distributed in those places 

Obviously, we dealing with non-constant variance or heteroskedasticity.
Let's use the varConstPower(), and varConstPower() is representing a constant plus power variance function structure, check this source: https://www.rdocumentation.org/packages/nlme/versions/3.1-152/topics/varConstPower.

let's create a model using Generalized Least Squares or gls for short and its generalized of OLS(ordinary least squares)

```
#gls model weights
gls_model <- gls(Calories ~ TotalDistance + VeryActiveMinutes, data=corDaily, 
                 weights = varConstPower())
```

summary of gls_model

```
summary(gls_model)

```
plot the gls_model.

```
plot(gls_model)

```

#### CREATE MODEL IN HOURLYACTIVITY

let's see if the Total steps and average intensity can predict the Calories in terms of hours.

```
reg_hour <- lm(Calories ~ AverageIntensity + TotalIntensity , data =  corhourly)

```

summary of reg_hour.

```

summary(reg_hour)

```

both the Average intensity and TotalIntensity have p-value greater than the significant level of 0.05
 let's plot the model
 
```

plot(reg_hour)

```
 
Note that we can't predict the Calories from either DailyActivity nor HourlyActivity, because need more data.

### Key Findings:

-Total steps or TotalDistance can affect calories but there are other features that also affect calories,  we can't find them in this analysis.

-we can say that average intensity can help us to see how all types of activity and the activity, whether this type of activity is walking, running, or even exercising how affect the Calories, so as the intensity of certain types of Activity or all of them increase the Calories that burned increase too.

-knowing the type of activity of each Id and their sleep quality can help a lot to build this Id to give him the right recommendation by using machine learning tools like the recommender system.

### high-level recommendations: 

-In order to build a strong marketing strategy we need more data because we need to know the precise need of the customer,
therefore we can say that we can help the customer reach their needs by letting them specify their goals via our product such as step goals, or how much calories they need to lose or gain weight, we can give him o notice that if their body mass
index are over-weight or under-weight, what they need to do about that.

