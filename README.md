# Proyecto-Capstone-data-analysis
## Introduction
Welcome to the Cyclistic shared bike analysis case study. In this case study, I will be performing many real-world tasks typical of a junior data analyst. I will be working for a fictional company called Cyclistic and meeting different characters and team members. To answer the company's key questions, I will follow the steps of the data analysis process:
* Ask.
* Prepare.
* Process.
* Analyze.
* Share.
* Act.
## Scenario
I am a junior data analyst working on the marketing analytics team at Cyclistic, a bike-sharing company in Chicago. The marketing director believes that the company's future success depends on maximizing the number of annual memberships. Therefore, my team wants to understand the differences in the usage of Cyclistic bikes between casual riders and annual members. Through these insights, my team will design a new marketing strategy to convert casual riders into annual members. However, before that, Cyclistic executives must approve my recommendations, so I must back up my proposal with compelling data insights and professional visualizations of the data.

## Characters and Teams
* **Cyclistic:** A bike-sharing program that includes 5,800 bikes and 600 stations. Cyclistic is notable for also offering recumbent bikes, hand tricycles, and cargo bikes, providing a more inclusive use of shared bikes for people with disabilities and cyclists who cannot use a standard two-wheel bike. Most cyclists choose traditional bikes, with about 8% of cyclists using assisted options. Cyclistic users are more likely to use bikes for recreation, but around 30% use them to commute to work every day.
* **Lily Moreno:** The marketing director and your manager. Moreno is responsible for developing campaigns and initiatives to promote the bike-sharing program. Campaigns may include email, social media, and other channels.
* **Cyclistic Marketing Data Analytics Team:** A team of data analysts responsible for collecting, analyzing, and reporting data that helps drive Cyclistic's marketing strategy. You joined this team six months ago and have focused not only on understanding Cyclistic's mission and business goals but also on figuring out how you can help Cyclistic achieve them from your position as a junior data analyst.
* **Cyclistic Executive Team:** The highly detail-oriented executive team will decide whether to approve the recommended marketing program.

## About the Company
In 2016, Cyclistic launched a successful bike-sharing program. Since then, the program has grown to a fleet of 5,824 GPS-enabled bikes locked in a network of 692 stations across Chicago. Bikes can be unlocked at one station and returned to any other station in the system at any time.

So far, Cyclistic's marketing strategy has been focused on building general brand awareness and attracting large consumer segments. One of the approaches that helped make this possible was the flexibility of its pricing plans: single ride passes, full-day passes, and annual memberships. Customers who buy single ride or full-day passes are called casual riders. Customers who buy annual memberships are called Cyclistic members.

Cyclistic's financial analysts concluded that annual members are much more profitable than casual riders. Although the flexible pricing helps Cyclistic attract more customers, Moreno believes that maximizing the number of annual members will be key to future growth. Instead of creating a marketing campaign targeting all new customers, Moreno believes there are many opportunities to convert casual riders into members. She points out that casual riders are already familiar with the Cyclistic program and have chosen Cyclistic for their mobility needs.

Moreno set a clear goal: Design marketing strategies aimed at converting casual riders into annual members. However, to do that, the marketing analytics team needs to better understand how annual members and casual riders differ, why casual riders would purchase a membership, and how digital media could impact their marketing tactics. Moreno and her team are interested in analyzing Cyclistic's historical bike trip data to identify trends.

## Business Task
Moreno assigned me this question: What are the differences between annual members and casual riders in terms of their use of Cyclistic bikes?
I need to identify key differences between the two user groups that can help determine how to encourage casual riders to become members, and how digital media could impact Cyclistic's marketing tactics.

## Data sources

* The data used in this project was provided by [Motivate International Inc.](https://divvy-tripdata.s3.amazonaws.com/index.html) under a [public license](https://divvybikes.com/data-license-agreement). This data has been adapted for the Cyclistic case study, a fictional company. The historical bike trip data covers the past 12 months and was downloaded in CSV format from the provided official site, with each file representing a month. The datasets include detailed information about the trips, such as start and end times, duration, type of bike used (classic or electric), and user type (member or casual rider).

* The data is public and available under a specific license. This license has been respected, and no personally identifiable information has been used in the analysis.

* The data is organized in CSV format, with columns that include trip identifiers, start and end times, origin and destination stations, bike type, and user type.

* The data is considered reliable since it comes from a widely recognized official source. Additionally, the consistency of trip dates and durations has been verified, ensuring that the data accurately represents the behavior of shared bike users.

## Data cleaning and manipulation in R.

* Install required packages
* tidyverse for data import and wrangling
* lubridate for date functions
* ggplot for visualization
```{r}
library(tidyverse)  #helps wrangle data
library(lubridate)  #helps wrangle date attributes
library(ggplot2)  #helps visualize data
getwd() #displays your working directory
setwd("/Users/carme/Desktop/Datos_Divvy/CSV") #sets your working directory to simplify calls to data ... make sure to use your OWN username instead of mine ;)
```
* Upload Divvy datasets (csv files) here
```{r}
enero <- read_csv("202401-divvy-tripdata.csv")
febrero <- read_csv("202402-divvy-tripdata.csv")
marzo <- read_csv("202403-divvy-tripdata.csv")
abril <- read_csv("202404-divvy-tripdata.csv")
mayo <- read_csv("202405-divvy-tripdata.csv")
junio <- read_csv("202406-divvy-tripdata.csv")
julio <- read_csv("202407-divvy-tripdata.csv")
agosto <- read_csv("202408-divvy-tripdata.csv")
septiembre <- read_csv("202409-divvy-tripdata.csv")
octubre <- read_csv("202410-divvy-tripdata.csv")
noviembre <- read_csv("202411-divvy-tripdata.csv")
diciembre <- read_csv("202412-divvy-tripdata.csv")
```
* Compare column names each of the files
* While the names don't have to be in the same order, they DO need to match perfectly before we can use a command to join them into one file
```{r}
colnames(enero)
colnames(febrero)
colnames(marzo)
colnames(abril)
colnames(mayo)
colnames(junio)
colnames(julio)
colnames(agosto)
colnames(septiembre)
colnames(octubre)
colnames(noviembre)
colnames(diciembre)
```
* Rename columns  to make them consistent with q1_2020 (as this will be the supposed going-forward table design for Divvy)
```{r}

(enero <- rename(enero
                   ,ride_id = trip_id
                   ,rideable_type = bikeid 
                   ,started_at = start_time  
                   ,ended_at = end_time  
                   ,start_station_name = from_station_name 
                   ,start_station_id = from_station_id 
                   ,end_station_name = to_station_name 
                   ,end_station_id = to_station_id 
                   ,member_casual = usertype))

(febrero <- rename(febrero
                   ,ride_id = trip_id
                   ,rideable_type = bikeid 
                   ,started_at = start_time  
                   ,ended_at = end_time  
                   ,start_station_name = from_station_name 
                   ,start_station_id = from_station_id 
                   ,end_station_name = to_station_name 
                   ,end_station_id = to_station_id 
                   ,member_casual = usertype))
(marzo <- rename(marzo
                   ,ride_id = trip_id
                   ,rideable_type = bikeid 
                   ,started_at = start_time  
                   ,ended_at = end_time  
                   ,start_station_name = from_station_name 
                   ,start_station_id = from_station_id 
                   ,end_station_name = to_station_name 
                   ,end_station_id = to_station_id 
                   ,member_casual = usertype))
#etc
...
```
* Inspect the dataframes and look for incongruencies
```{r}

str(enero)
str(febrero)
str(marzo)
...
```
* Convert ride_id and rideable_type to character so that they can stack correctly
```{r}
enero <-  mutate(enero, ride_id = as.character(ride_id)
                   ,rideable_type = as.character(rideable_type)) 
febrero <-  mutate(febrero, ride_id = as.character(ride_id)
                   ,rideable_type = as.character(rideable_type)) 
marzo <-  mutate(marzo, ride_id = as.character(ride_id)
                   ,rideable_type = as.character(rideable_type))
...
```
* Stack individual quarter's data frames into one big data frame
```{r}
all_trips <- bind_rows(enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre)
```
* Inspect the new table that has been created
```{r}
colnames(all_trips)  #List of column names
nrow(all_trips)  #How many rows are in data frame?
dim(all_trips)  #Dimensions of the data frame?
head(all_trips)  #See the first 6 rows of data frame.  Also tail(all_trips)
str(all_trips)  #See list of columns and data types (numeric, character, etc)
summary(all_trips)  #Statistical summary of data. Mainly for numerics
```
* Remove irrelevant columns.
```{r}
all_trips <- all_trips[, !(names(all_trips) %in% c("start_lat", "start_lng", "end_lat", "end_lng"))]
```
* Remove duplicate rows
```{r}
all_trips <- unique(all_trips)
```

There are a few problems we will need to fix:
* The data can only be aggregated at the ride-level, which is too granular. We will want to add some additional columns of data -- such as day_of_month, month, year -- that provide additional opportunities to aggregate the data.
* We will want to add a calculated field for length of ride since the 2020Q1 data did not have the "tripduration" column. We will add "ride_length" to the entire dataframe for consistency.
*There are some rides where tripduration shows up as negative, including several hundred rides where Divvy took bikes out of circulation for Quality Control reasons. We will want to delete these rides.
* Add columns that list the date, month, day, and year of each ride
* This will allow us to aggregate ride data for each month, day, or year ... before completing these operations we could only aggregate at the ride level
```{r}
all_trips$date <- as.Date(all_trips$started_at) #The default format is yyyy-mm-dd
all_trips$month <- format(as.Date(all_trips$date), "%m")
all_trips$day_of_month <- format(as.Date(all_trips$date), "%d")
all_trips$year <- format(as.Date(all_trips$date), "%Y")
all_trips$day_of_week <- format(as.Date(all_trips$date), "%A")
```
* Add a "ride_length" calculation to all_trips (in seconds)
```{r}
all_trips$ride_length <- difftime(all_trips$ended_at,all_trips$started_at)
```

* Inspect the structure of the columns
```{r}
str(all_trips)
```
* Convert "ride_length" from Factor to numeric so we can run calculations on the data
```{r}
is.factor(all_trips$ride_length)
all_trips$ride_length <- as.numeric(as.character(all_trips$ride_length))
is.numeric(all_trips$ride_length)
```
* Remove "bad" data
* The dataframe includes a few hundred entries when bikes were taken out of docks and checked for quality by Divvy or ride_length was negative
* We will create a new version of the dataframe (v2) since data is being removed
```{r}
all_trips_v2 <- all_trips[!(all_trips$start_station_name == "HQ QR" | all_trips$ride_length<0),]
```
















