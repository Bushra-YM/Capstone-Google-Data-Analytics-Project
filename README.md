# Google Data Analytics Capstone: Cyclistic Case Study

## Course [Google Data Analytics Professional Certificate](https://www.coursera.org/enroll/google-data-analytics/paidmedia?utm_medium=sem&utm_source=gg&utm_campaign=B2C_NAMER_google-data-analytics_google_FTCOF_professional-certificates_country-US&campaignid=12504215975&adgroupid=122709142727&device=c&keyword=google%20data%20analytics%20certificate&matchtype=b&network=g&devicemodel=&adposition=&creativeid=668441307530&hide_mobile_promo&gclid=CjwKCAiAk9itBhASEiwA1my_6z4jzzJtshiam6g7ibLpd_ckSBQ6_vLNqUwDlIRpdgLKrnjDr4iQFxoCAnQQAvD_BwE)


# Introduction


I've been learning about data analysis with the Google Data Analytics Certificate courses on Coursera. This project is the final result of my efforts. I'll be using Excel, SQL, Big Query, and Tableau to explore and compare ride-share patterns between annual members and casual riders. I am Bushra Mihdawi, and this project is a testament to my newfound skills in data analysis.


Links to code and visuals will be posted at the bottom of the page, but I will include them here for convenience as well.
SQL Code : [link]( https://github.com/Bushra-YM/Capstone-Google-Data-Analytics-Project)

Tableau Visual:[Link](https://public.tableau.com/app/profile/bushra.mihdawi/viz/BUSHRAYOUSEF/TotalTrips#1) 


## Links 

### Data Source [Divvy_tripdata](https://divvy-tripdata.s3.amazonaws.com/index.html)

### SQL Queries

[1-Data Combine](https://github.com/Bushra-YM/Capstone-Google-Data-Analytics-Project/blob/main/1-Data%20Combine)

[2-Data Exploration](https://github.com/Bushra-YM/Capstone-Google-Data-Analytics-Project/blob/main/3-Data%20Exploration)

[3-Data Cleaning](https://github.com/Bushra-YM/Capstone-Google-Data-Analytics-Project/blob/main/2-Data%20Cleaning)

[4-Data Analysis](https://github.com/Bushra-YM/Capstone-Google-Data-Analytics-Project/blob/main/4-%20Data%20Analysis)




## Background

Cyclistic operates a bike-sharing program with over 5,800 bikes and 600 docking stations, providing inclusive options like reclining bikes and hand tricycles. Established in 2016, the program has expanded to 692 tracked stations across Chicago, allowing users to unlock and return bikes at any station.
Historically, Cyclistic focused on broad consumer awareness, offering various pricing plans such as single-ride passes, full-day passes, and annual memberships. Casual riders, opting for single-ride or full-day passes, coexist with Cyclistic members, who subscribe annually.


## My Role

As a junior data analyst at Cyclistic, my team is tasked with developing marketing strategies targeting the conversion of casual riders into annual members.


## Overall Goal


Devise effective marketing strategies to encourage casual riders to become Cyclistic annual members.

## Business Questions 

How do the behaviors of annual members and casual riders differ in their use of Cyclistic bikes?" The following sections outline the step-by-step approach employed in addressing this project.



## Ask:

### Business Task


I'll examine data on how current Cyclistic bike users use the bikes, looking for patterns like usage frequency and other trends. This analysis aims to understand the general habits of two customer groups: annual members and casual riders.

## Prepare: Data Source Description


The information used to address the business question was sourced directly from Cyclistic's internal metrics [Divvy_tripdata](https://divvy-tripdata.s3.amazonaws.com/index.html), capturing data from its stations and bikes. The data has been made available by
Motivate International Inc. under this [license](https://divvybikes.com/data-license-agreement).

The dataset spans a 12-month duration, from January 2023 to December 2023, organized into individual files for each month. Each table includes 13 columns, featuring ride IDs, bike types, ride start and end times, station identifiers (including name and location), and the rider's membership type.

![Screenshot 2024-01-11 120852](https://github.com/Bushra-YM/Capstone-Google-Data-Analytics-Project/assets/156461228/4e86832e-529c-4608-b6b7-895b8a47ce01)

The data is generally unbiased, except for the absence of start and end location data for numerous rides. After a thorough inquiry, it was determined that information for these specific stations was unavailable. I downloaded each monthly CSV file and converted them into .xlsx files for utilization in Excel.


## Process:


After acquiring the data, I examined each file separately in Excel to understand its structure. Given the extensive size of the data, I opted to clean each month's information independently in Excel before attempting any data merging. The following outlines the cleaning process:
Examined all rows in each file for duplicates using Excel's built-in feature, and no duplicates were identified.

![Screenshot 2024-01-11 122615](https://github.com/Bushra-YM/Capstone-Google-Data-Analytics-Project/assets/156461228/d67286ee-526a-410e-a840-0c83ac1d6000)


                                                  Example of duplicate check results for May data



I employed conditional formatting to highlight blank cells in gray, facilitating the identification of missing data. Subsequently, rows with incomplete information for both start and end station locations in several trips were excluded from the dataset.

![Screenshot 2024-01-11 123430](https://github.com/Bushra-YM/Capstone-Google-Data-Analytics-Project/assets/156461228/5231d782-61c0-401e-99eb-649d84144331)



                                                  Empty fields were identified for station names.


Established a new column called "ride_length" to determine the duration of each bike ride in minutes. This involved calculating the time difference between the end and start times.


![Screenshot 2024-01-11 125519](https://github.com/Bushra-YM/Capstone-Google-Data-Analytics-Project/assets/156461228/53259bf9-82a2-4cef-a9a7-06bb7982a8e6)



Established a new column called "day_of_week" to extract the day name from each start time and saved it as a numerical representation ranging from 1 to 7.


![Screenshot 2024-01-11 164007](https://github.com/Bushra-YM/Capstone-Google-Data-Analytics-Project/assets/156461228/f2056a53-0b1b-436b-8111-da78b89f736d)



I reviewed the maximum and minimum values in all rows to identify outliers. During this examination, I found negative times, and it became evident that Daylight Saving Time (DST) had affected the recorded ride lengths. To address this issue, I introduced a new formula specifically for these rides to rectify the ride length data.


![Screenshot 2024-01-11 125903](https://github.com/Bushra-YM/Capstone-Google-Data-Analytics-Project/assets/156461228/f63a1b93-ed3a-4202-8da3-6fb27bd48ed7)


                                                 Negative ride times caused by DST time change




Identified and eliminated rows with zero-minute ride times. Subsequently, removed any remaining negative ride times from the dataset.
Conducted a count of distinct ride IDs to ensure uniqueness, and verified that the calculated count aligned with the number of rows in each dataset.

### Note: 
           Please be aware that additional cleaning tasks were carried out later in the process to address unexpected issues. Refer to the SQL code in the next section to observe any cleaning actions taken on the combined data.
 

## Analysis of Data Through Big Query and Tableau

### Combining the Data

SQL Query :[Data Combine](https://github.com/Bushra-YM/Capstone-Google-Data-Analytics-Project/blob/main/1-Data%20Combine) 

We use BigQuery to bring together and clean up different datasets. This is because Microsoft Excel can only handle up to 1,048,576 rows, and since the Cyclistic dataset has over 5.6 million rows, we need a platform like BigQuery that can handle such large amounts of data.

Tables for 12 CSV files have been added to the '2023_tripdata' dataset. Furthermore, a table named "combined_data" has been established, encompassing a total of 5,719,877 rows of data representing the entire year.



### Data Exploration 
SQL Query :[Data Exploration](https://github.com/Bushra-YM/Capstone-Google-Data-Analytics-Project/blob/main/2-Data%20Exploration)

1-  The following table displays the names of all columns along with their corresponding data types.

![Screenshot 2024-01-23 161007](https://github.com/Bushra-YM/Capstone-Google-Data-Analytics-Project/assets/156461228/234f7149-d3d2-42e7-aa08-21108f3187fc)


2- The table below illustrates the count of null values in each column.

![Screenshot 2024-01-23 161832](https://github.com/Bushra-YM/Capstone-Google-Data-Analytics-Project/assets/156461228/c72894e0-6d3b-4dbe-871f-a086bccdfe96)


3- Since ride_id has no null values, we can utilize it to identify and check for duplicates.

![Screenshot 2024-01-23 162407](https://github.com/Bushra-YM/Capstone-Google-Data-Analytics-Project/assets/156461228/cb033d66-9b27-49e5-9f30-74b3cf7e03fd)


 4- The columns started_at and ended_at display the trip's start and end times in the YYYY-MM-DD hh:mm:ss UTC format. To determine the overall trip duration, a new column named ride_length can be generated.


## Data Cleaning

SQL Query[Data Cleaning](https://github.com/Bushra-YM/Capstone-Google-Data-Analytics-Project/blob/main/2-Data%20Cleaning)

1- Rows containing missing values have been removed.

2- Trips with a duration of less than a minute or longer than a day have been excluded.

3- During this step, 1,476,445 rows in total have been removed.


## Analyze and Share

SQL Query[Data Analysis](https://github.com/Bushra-YM/Capstone-Google-Data-Analytics-Project/blob/main/4-%20Data%20Analysis)

Data Visualization:

The data has been organized and is now ready for analysis. I performed queries on various pertinent tables and visualized the results using Tableau.
The initial analysis involves comparing member and casual riders, focusing on the types of bikes they use.


![Screenshot 2024-01-23 202908](https://github.com/Bushra-YM/Capstone-Google-Data-Analytics-Project/assets/156461228/497e2c1e-c3c0-4b20-8f28-d0950b854b48)




More than half (64.53%) of the riders are members, and the rest (35.47%) are casual riders. The percentage charts for each bike type show how much they are used compared to the total. Classic bikes are the most popular, followed by electric bikes. Docked bikes are used the least, mostly by casual riders.


#### Next, we analyze the distribution of trips based on months and days of the week.

![Screenshot 2024-01-23 204154](https://github.com/Bushra-YM/Capstone-Google-Data-Analytics-Project/assets/156461228/88489eee-a603-468f-9b05-415d2ccb53d9)


![Screenshot 2024-01-24 172630](https://github.com/Bushra-YM/Capstone-Google-Data-Analytics-Project/assets/156461228/b46d3085-bdc9-4ee2-b6e1-ba8a4b89b1d5)


### Monthly: In terms of monthly trips, both casual riders and members demonstrate similar trends, with increased trips in spring and summer and reduced activity in winter. The distinction between casual riders and members is minimal, particularly during July in the summer season.


### Weekly: When examining days of the week, it's observed that casual riders increase their trips on weekends, while members, although experiencing a decline over the weekend, still make the most journeys compared to other days of the week.


### Hourly: The data indicates two notable peaks in the number of trips for members: one during the early morning hours (around 6 am to 8 am) and another in the evening (around 4 pm to 8 pm). In contrast, casual riders display a gradual increase in trip numbers throughout the day, peaking in the evening and tapering off later.


From these observations, we can infer that members likely use bikes for commuting to and from work on weekdays, while casual riders prefer bikes consistently throughout the day, with a higher usage frequency on weekends for leisure. Both groups exhibit heightened activity during the summer and spring seasons.
To delve deeper into the distinctions in behavior between casual and member riders, an analysis of the durations of their respective trips can provide valuable insights.
 

## Average Ride Durations Monthly/Weekly/Hourly  in 2023 Trips

![Screenshot 2024-01-24 174556](https://github.com/Bushra-YM/Capstone-Google-Data-Analytics-Project/assets/156461228/9f69daba-08ce-4a34-9eb3-97fa1d898b7e)

![Screenshot 2024-01-24 174733](https://github.com/Bushra-YM/Capstone-Google-Data-Analytics-Project/assets/156461228/893eac6d-04d6-4629-889e-50c91294f21a)




It's noteworthy that casual riders, on average, have longer cycling durations compared to members. The average journey length for members remains consistent throughout the year, week, and day. In contrast, casual riders exhibit variations in their cycling durations. They cover greater distances in the spring and summer, on weekends, and between 10 am to 2 pm during the day. Additionally, their trips tend to be brief between five and eight in the morning.

These findings lead to the conclusion that casual commuters cover longer distances (approximately twice as much) but with less frequency compared to members. Their longer journeys on weekends, during the day outside of commuting hours, and in the spring and summer seasons suggest a recreational purpose behind their cycling activities.


To gain a deeper understanding of the distinctions between casual and member riders, an analysis of the starting and ending station locations can provide valuable insights. By applying filters to identify stations with the highest trip frequencies, we can draw conclusions based on the following observations.


## Total Trips Start Locations in 2023

![Screenshot 2024-01-24 180805](https://github.com/Bushra-YM/Capstone-Google-Data-Analytics-Project/assets/156461228/227ee580-aa53-4cc1-9ca5-ed2dd247c100)




## Total Trips End Locations in 2023

![Screenshot 2024-01-24 181841](https://github.com/Bushra-YM/Capstone-Google-Data-Analytics-Project/assets/156461228/68a5cadf-c6f9-4eec-a8e7-6cff8450312e)




Casual riders frequently choose to start their trips from stations situated near museums, parks, beaches, harbor points, and aquariums. Notably, the Chicago Harbor stands out as a prominently attended location for commencing trips, drawing considerable attention from casual riders as a preferred starting point for their journeys. In contrast, members tend to initiate their journeys from stations near universities, residential areas, restaurants, hospitals, grocery stores, theaters, schools, banks, factories, train stations, parks, and plazas. This distinction in starting station locations suggests diverse preferences and purposes for bike usage between casual and member riders.


When it comes to where riders finish their trips, a similar pattern emerges. Casual riders often end their journeys near parks, museums, and other fun places, showing a preference for leisure. On the other hand, members finish their trips near universities, residential areas, and business areas, suggesting a trend of using bikes for everyday commuting. This difference in where they end their trips supports the idea that casual riders mainly use bikes for fun, while members rely on them a lot for their daily commutes.



## Summary

|Casual |Member|
|------|-------|
|1- Casual riders engage in longer, less frequent rides, indicating a preference for leisure and recreational activities.|1- Members engage in more frequent rides, but the duration of their trips is shorter, approximately half of the trip duration observed in casual riders.|     
|2- They tend to start and end their journeys near recreational sites such as parks, museums, and along the coast.|2- The starting and ending points of members' trips are often close to universities, residential areas, and commercial zones, emphasizing their inclination toward using bikes for daily commuting purposes|
|3- Casual riders prefer using bikes consistently throughout the day, with a notable increase in activity over weekends in the summer and spring.|3- Members prefer bike rides on weekdays, particularly during commute hours between 8 am and 5 pm, and this trend is more prominent in the summer and spring seasons.|



## Act

Once we understand how casual and member riders differ, we can create marketing plans to attract casual riders and encourage them to become members.

### 1- Acknowledge that casual riders tend to use their bikes for longer durations than members and consider introducing discounts for extended rides to incentivize both casual riders and members to opt for longer journeys.

### 2- Recognize the peak activity of casual riders on weekends and during the summer and spring, leading to the potential offering of seasonal or weekend-only memberships.

### 3- Explore partnership opportunities, such as bundled membership deals with other transportation modes like elevated trains or buses, to attract commuters.

### 4- Conduct targeted marketing campaigns during spring and summer at tourist and recreational locations popular among casual riders.

### 5- Reevaluate the marketing approach for students in the area, considering a more student-friendly membership aligned with the academic calendar to boost memberships among college students who rely on bikes for commuting to class.

### 6- Tailor marketing campaigns for classic bike riders, focusing on promoting biking opportunities lasting around 20 minutes in nearby areas like parks or bike paths.













































