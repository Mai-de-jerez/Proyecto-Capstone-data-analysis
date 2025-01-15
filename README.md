# PROYECTO CAPSTONE DATA ANALYSIS

## INTRODUCTION

Welcome to the Cyclistic shared bike analysis case study. In this case study, I will be performing many real-world tasks typical of a junior data analyst. I will be working for a fictional company called Cyclistic and meeting different characters and team members. To answer the company's key questions, I will follow the steps of the data analysis process:
* Ask.
* Prepare.
* Process.
* Analyze.
* Share.
* Act.
  
## SCENARIO

I am a junior data analyst working on the marketing analytics team at Cyclistic, a bike-sharing company in Chicago. The marketing director believes that the company's future success depends on maximizing the number of annual memberships. Therefore, my team wants to understand the differences in the usage of Cyclistic bikes between casual riders and annual members. Through these insights, my team will design a new marketing strategy to convert casual riders into annual members. However, before that, Cyclistic executives must approve my recommendations, so I must back up my proposal with compelling data insights and professional visualizations of the data.

## CHARACTERS AND TEAM

* **Cyclistic:** A bike-sharing program that includes 5,800 bikes and 600 stations. Cyclistic is notable for also offering recumbent bikes, hand tricycles, and cargo bikes, providing a more inclusive use of shared bikes for people with disabilities and cyclists who cannot use a standard two-wheel bike. Most cyclists choose traditional bikes, with about 8% of cyclists using assisted options. Cyclistic users are more likely to use bikes for recreation, but around 30% use them to commute to work every day.
* **Lily Moreno:** The marketing director and your manager. Moreno is responsible for developing campaigns and initiatives to promote the bike-sharing program. Campaigns may include email, social media, and other channels.
* **Cyclistic Marketing Data Analytics Team:** A team of data analysts responsible for collecting, analyzing, and reporting data that helps drive Cyclistic's marketing strategy. You joined this team six months ago and have focused not only on understanding Cyclistic's mission and business goals but also on figuring out how you can help Cyclistic achieve them from your position as a junior data analyst.
* **Cyclistic Executive Team:** The highly detail-oriented executive team will decide whether to approve the recommended marketing program.

## ABOUT THE COMPANY

In 2016, Cyclistic launched a successful bike-sharing program. Since then, the program has grown to a fleet of 5,824 GPS-enabled bikes locked in a network of 692 stations across Chicago. Bikes can be unlocked at one station and returned to any other station in the system at any time.

So far, Cyclistic's marketing strategy has been focused on building general brand awareness and attracting large consumer segments. One of the approaches that helped make this possible was the flexibility of its pricing plans: single ride passes, full-day passes, and annual memberships. Customers who buy single ride or full-day passes are called casual riders. Customers who buy annual memberships are called Cyclistic members.

Cyclistic's financial analysts concluded that annual members are much more profitable than casual riders. Although the flexible pricing helps Cyclistic attract more customers, Moreno believes that maximizing the number of annual members will be key to future growth. Instead of creating a marketing campaign targeting all new customers, Moreno believes there are many opportunities to convert casual riders into members. She points out that casual riders are already familiar with the Cyclistic program and have chosen Cyclistic for their mobility needs.

Moreno set a clear goal: Design marketing strategies aimed at converting casual riders into annual members. However, to do that, the marketing analytics team needs to better understand how annual members and casual riders differ, why casual riders would purchase a membership, and how digital media could impact their marketing tactics. Moreno and her team are interested in analyzing Cyclistic's historical bike trip data to identify trends.

## BUSINESS TASK

Moreno assigned me this question: What are the differences between annual members and casual riders in terms of their use of Cyclistic bikes?
I need to identify key differences between the two user groups that can help determine how to encourage casual riders to become members, and how digital media could impact Cyclistic's marketing tactics.

## DATA SOURCES

* The data used in this project was provided by [Motivate International Inc.](https://divvy-tripdata.s3.amazonaws.com/index.html) under a [public license](https://divvybikes.com/data-license-agreement). This data has been adapted for the Cyclistic case study, a fictional company. The historical bike trip data covers the past 12 months and was downloaded in CSV format from the provided official site, with each file representing a month. The datasets include detailed information about the trips, such as start and end times, duration, type of bike used (classic or electric), and user type (member or casual rider).

* The data is public and available under a specific license. This license has been respected, and no personally identifiable information has been used in the analysis.

* The data is organized in CSV format, with columns that include trip identifiers, start and end times, origin and destination stations, bike type, and user type.

* The data is considered reliable since it comes from a widely recognized official source. Additionally, the consistency of trip dates and durations has been verified, ensuring that the data accurately represents the behavior of shared bike users.

## DATA WRANGLING IN R

1. Load the CSV files into R and merge them into a single data frame.
2. Delete the columns start_lat, start_lng, end_lat and end_lng, because they seem irrelevant to me.
3. Convert the started_at column to "Date".
4. Create new columns for the year (year), the month (month), the day of the week (day_of_week) and the day of the month (day).
5. Create a column called ride_length to measure the duration of the ride in seconds.
6. Convert the ride_length column to a numeric data type.
7. Remove duplicate rows from the data frame.
8. Create a new data frame that does not include trips shorter than 60sec.
9. Change the values ​​of the Month column so that it contains month names instead of numbers.

## DATA ANALYSIS IN R

1. Statistical summary of the ride_length column.
2. Count the number of trips for each user.
3. Analize the duration of the trip depending on the type of user.
4. Analize the duration of the trip depending on the day of the week and the type of user.
5. Analize the duration of the trip and the number of trips according to the type of user and the day of the week.
6. Analize the duration of the trip and the number of trips according to the type of user and the month.

**Findings:**

**Casual users:**

* They take fewer trips overall than members.
* They make more trips on weekends and during the summer, and tend to make more trips in the afternoon.
* They take longer trips in general, twice as long. 
* Their trips are longer during the day, on weekends, and in the spring-summer seasons.
* This suggests recreational use of bicycles, probably students and retirees.

**Member users:**

* They make more trips in general than casual users.
* They make more trips during the week, in summer, and the times at which they make the most trips are 8AM and 6PM.
* They take shorter trips, approximately half as long as casual users.
* Their trips are almost always of the same duration, somewhat less overnight. 
* They do not vary their duration significantly between the different seasons, but they make slightly longer trips on weekends.
* This suggests that they are users who use bikes to go to work, whether during the day shift or the night shift, which is why the times they make the most trips coincide with the opening and closing hours of businesses.

## DATA VISUALIZATIONS


### RECOMENDATIONS

* Offer a type of membership to casual users called 'free time' that allows them to use the bikes during the afternoon, from 4PM to 10PM for example, on weekends all day, and unlimited access during the day in the summer months.

* Create a marketing campaign focused on these benefits, clear messages about the hours and days that users can enjoy their membership, and how this will allow them to have a more flexible experience that fits their lives, across networks social events, advertising messages at bus stops (to raise awareness about the importance of the environment), and advertising messages near secondary schools, universities, and nursing homes.

* One of the key strategies for converting casual cyclists into annual Cyclistic members is to leverage the existing network of users. A referral system would incentivize current users to refer their friends and family to join the annual membership program. This marketing strategy can leverage the trust and personal relationships of current riders to attract new members. Every time a referral signs up for an annual membership, both the current user and the new member would receive a reward, such as a month of Free membership or a discount on future renewals. This type of incentive would motivate members to share the program with others.



















