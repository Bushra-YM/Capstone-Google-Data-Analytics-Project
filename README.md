# Google Data Analytics Capstone: Cyclistic Case Study

## Course [Google Data Analytics Professional Certificate](https://www.coursera.org/enroll/google-data-analytics/paidmedia?utm_medium=sem&utm_source=gg&utm_campaign=B2C_NAMER_google-data-analytics_google_FTCOF_professional-certificates_country-US&campaignid=12504215975&adgroupid=122709142727&device=c&keyword=google%20data%20analytics%20certificate&matchtype=b&network=g&devicemodel=&adposition=&creativeid=668441307530&hide_mobile_promo&gclid=CjwKCAiAk9itBhASEiwA1my_6z4jzzJtshiam6g7ibLpd_ckSBQ6_vLNqUwDlIRpdgLKrnjDr4iQFxoCAnQQAvD_BwE)


# Introduction


I've been learning about data analysis with the Google Data Analytics Certificate courses on Coursera. This project is the final result of my efforts. I'll be using Excel, SQL, Big Query, and Tableau to explore and compare ride-share patterns between annual members and casual riders. I am Bushra Mihdawi, and this project is a testament to my newfound skills in data analysis.


Links to code and visuals will be posted at the bottom of the page, but I will include them here for convenience as well.
SQL Code : [link]( https://github.com/Bushra-YM/Capstone-Google-Data-Analytics-Project)

Tableau Visual: 



## Background

Cyclistic operates a bike-sharing program with over 5,800 bikes and 600 docking stations, providing inclusive options like reclining bikes and hand tricycles. Established in 2016, the program has expanded to 692 tracked stations across Chicago, allowing users to unlock and return bikes at any station.
Historically, Cyclistic focused on broad consumer awareness, offering various pricing plans such as single-ride passes, full-day passes, and annual memberships. Casual riders, opting for single-ride or full-day passes, coexist with Cyclistic members, who subscribe annually.


## My Role

As a junior data analyst at Cyclistic, my team is tasked with developing marketing strategies targeting the conversion of casual riders into annual members.


## Overall Goal


Devise effective marketing strategies to encourage casual riders to become Cyclistic annual members.
## Business Questions 

How do the behaviors of annual members and casual riders differ in their use of Cyclistic bikes?" The following sections outline the step-by-step approach employed in addressing this project.



## Ask: Business Task


I'll examine data on how current Cyclistic bike users use the bikes, looking for patterns like usage frequency and other trends. This analysis aims to understand the general habits of two customer groups: annual members and casual riders.

## Prepare: Data Source Description


The information used to address the business question was sourced directly from Cyclistic's internal metrics, capturing data from its stations and bikes. The dataset spans a 5-month duration, from January 2023 to December 2023, organized into individual files for each month. Each table includes 13 columns, featuring ride IDs, bike types, ride start and end times, station identifiers (including name and location), and the rider's membership type.

![image](https://private-user-images.githubusercontent.com/156461228/300289305-83adba3b-4add-4489-8d8e-040985dfcce5.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDY0NzExNTQsIm5iZiI6MTcwNjQ3MDg1NCwicGF0aCI6Ii8xNTY0NjEyMjgvMzAwMjg5MzA1LTgzYWRiYTNiLTRhZGQtNDQ4OS04ZDhlLTA0MDk4NWRmY2NlNS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwMTI4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDEyOFQxOTQwNTRaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT04YWU3ZDM0OTk5NDVmNWE3NmUyYWFiODZlM2MzYzEyZDI3ZThiZDlkNzg3ZDdhMWU0NmU2OTk3MjdmZTZhYzE4JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.97AU3qjUxmpUmmDuhogALuPcFMJyMnm0yvVjGCZnJCY)

The data is generally unbiased, except for the absence of start and end location data for numerous rides. After a thorough inquiry, it was determined that information for these specific stations was unavailable. I downloaded each monthly CSV file and converted them into .xlsx files for utilization in Excel.


## Process: Cleaning the Data


After acquiring the data, I examined each file separately in Excel to understand its structure. Given the extensive size of the data, I opted to clean each month's information independently in Excel before attempting any data merging. The following outlines the cleaning process:
Examined all rows in each file for duplicates using Excel's built-in feature, and no duplicates were identified.

![image](https://private-user-images.githubusercontent.com/156461228/300294985-4464ef3e-6cb8-4769-b19f-088e96e2c695.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDY0Nzc2NzUsIm5iZiI6MTcwNjQ3NzM3NSwicGF0aCI6Ii8xNTY0NjEyMjgvMzAwMjk0OTg1LTQ0NjRlZjNlLTZjYjgtNDc2OS1iMTlmLTA4OGU5NmUyYzY5NS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwMTI4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDEyOFQyMTI5MzVaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0zZTE4YTk4NjViOGJhMTNmMmQ1YjNmOWQzNjQ3YjU3OTBkNWUyZWFhNDQ2ODJmZDMxOGY2NDgwZDkwZWQ4OWFkJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.jPfg9LfdYxPnPM7Kmg247h5-GwR3BU73IhqufeXTEOY)

                                                  Example of duplicate check results for May data



I employed conditional formatting to highlight blank cells in gray, facilitating the identification of missing data. Subsequently, rows with incomplete information for both start and end station locations in several trips were excluded from the dataset.

![image](https://private-user-images.githubusercontent.com/156461228/300295123-0fedb1ff-fdb6-41c1-8cf3-356fb55b9ece.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDY0Nzc4MjMsIm5iZiI6MTcwNjQ3NzUyMywicGF0aCI6Ii8xNTY0NjEyMjgvMzAwMjk1MTIzLTBmZWRiMWZmLWZkYjYtNDFjMS04Y2YzLTM1NmZiNTViOWVjZS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwMTI4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDEyOFQyMTMyMDNaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT03NDgwY2U0ODQ2OTkwMDYyYTJiNzVmYjk4M2MyOWU0ZGJhNDhjNmEwOTM4OGI3OTc1ZTYwNzE0MzQ0ZTQzZWY5JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.5NGV8KogQHWRtxot0k4qdRQ1bq04Ly75pt0d8cPCv0c)

                                                  Empty fields were identified for station names.


Established a new column called "ride_length" to determine the duration of each bike ride in minutes. This involved calculating the time difference between the end and start times.

![image](https://private-user-images.githubusercontent.com/156461228/300295222-d09ff59c-7fe0-4b6c-9b8d-260e898be004.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDY0Nzc5NjcsIm5iZiI6MTcwNjQ3NzY2NywicGF0aCI6Ii8xNTY0NjEyMjgvMzAwMjk1MjIyLWQwOWZmNTljLTdmZTAtNGI2Yy05YjhkLTI2MGU4OThiZTAwNC5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwMTI4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDEyOFQyMTM0MjdaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0wNGMzNjVhZWU3MmM5ODc2ZjNmZTAxMmQxMDhmMWEzN2Q1Y2UxNGY1YWYxODA1ZDNlZjA0OGM2OWM4NGYxM2MzJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.0hiuwiyaMoMXnB3aSB2-yd1qcqugY5fYs8nkm6VuBYw)


Established a new column called "day_of_week" to extract the day name from each start time and saved it as a numerical representation ranging from 1 to 7.

![IMAGE](https://private-user-images.githubusercontent.com/156461228/300295291-2b7fc16a-6eac-4c67-bb86-a5872c47341d.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDY0NzgwNTUsIm5iZiI6MTcwNjQ3Nzc1NSwicGF0aCI6Ii8xNTY0NjEyMjgvMzAwMjk1MjkxLTJiN2ZjMTZhLTZlYWMtNGM2Ny1iYjg2LWE1ODcyYzQ3MzQxZC5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwMTI4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDEyOFQyMTM1NTVaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1mODBlOWJjZmY0MTQ2MjNkMjk4MjA1NThlMzdlMDdhMWE0MGExNzk1ZDQ3YTkzYTY0MTRjMDY2MzUwYTZjZTU5JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.cSqyoi9KFyOtwDlSYGywYgWb5EWwDAqOCEr1WpsoEGo)


I reviewed the maximum and minimum values in all rows to identify outliers. During this examination, I found negative times, and it became evident that Daylight Saving Time (DST) had affected the recorded ride lengths. To address this issue, I introduced a new formula specifically for these rides to rectify the ride length data.

![IMAGE](https://private-user-images.githubusercontent.com/156461228/300295366-4bbdf2a3-8a46-4476-9ad1-6c9e92141b58.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDY0NzgxNDIsIm5iZiI6MTcwNjQ3Nzg0MiwicGF0aCI6Ii8xNTY0NjEyMjgvMzAwMjk1MzY2LTRiYmRmMmEzLThhNDYtNDQ3Ni05YWQxLTZjOWU5MjE0MWI1OC5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwMTI4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDEyOFQyMTM3MjJaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1iNjhlMzM2MTdmM2VlYzMzZTU5YjY4M2I1ZmFlMjQ3NGI3Mzg5ODRiMTUwNTZmYTVlNTAzMzZiYjk3NTI4MWQ2JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.WhblH2RNeYhBRpMIsIkf5YwMZ-WvbfRAOvxdQ8HfXLA)

                                                 Negative ride times caused by DST time change




Identified and eliminated rows with zero-minute ride times. Subsequently, removed any remaining negative ride times from the dataset.
Conducted a count of distinct ride IDs to ensure uniqueness, and verified that the calculated count aligned with the number of rows in each dataset.

### Note: 
           Please be aware that additional cleaning tasks were carried out later in the process to address unexpected issues. Refer to the SQL code in the next section to observe any cleaning actions taken on the combined data.

## Analyze and Share: Analysis of Data Through Big Query and Tableau

We use BigQuery to bring together and clean up different datasets. This is because Microsoft Excel can only handle up to 1,048,576 rows, and since the Cyclistic dataset has over 5.6 million rows, we need a platform like BigQuery that can handle such large amounts of data.


### Combining the Data
SQL Query:
Tables for 12 CSV files have been added to the '2023_tripdata' dataset. Furthermore, a table named "combined_data" has been established, encompassing a total of 5,719,877 rows of data representing the entire year.



### Findings:
1-  The following table displays the names of all columns along with their corresponding data types.

![IMAGE](https://private-user-images.githubusercontent.com/156461228/300295615-5b536a74-349a-4629-bb0b-5d5d57184cf0.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDY0Nzg0MjcsIm5iZiI6MTcwNjQ3ODEyNywicGF0aCI6Ii8xNTY0NjEyMjgvMzAwMjk1NjE1LTViNTM2YTc0LTM0OWEtNDYyOS1iYjBiLTVkNWQ1NzE4NGNmMC5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwMTI4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDEyOFQyMTQyMDdaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0wYWUxY2ZkMDNmNTJmYTU5MmZmMWM1NWNmZDIwMTg0ZGEwYWYwZmZiZDJmMjdkYTdlM2ZiNzI4OWRkZDhhNDc2JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.dZ9ZqBqR_sA8EYN0pvadaHgYDoGmHV-z4B5uzUwoUqk)

2- The table below illustrates the count of null values in each column.

![IMAGE](https://private-user-images.githubusercontent.com/156461228/300295659-8d1de443-aebf-4482-9bdb-11ae3afb0fa4.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDY0Nzg1MDMsIm5iZiI6MTcwNjQ3ODIwMywicGF0aCI6Ii8xNTY0NjEyMjgvMzAwMjk1NjU5LThkMWRlNDQzLWFlYmYtNDQ4Mi05YmRiLTExYWUzYWZiMGZhNC5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwMTI4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDEyOFQyMTQzMjNaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0wMDg2MTcwMzAxMTQ3MWZkOWJmNDc1ODllZWRiOTA5NmU3NmQzZWIzOWE5ZmNhNTI0ZTkxNTEzYzY0NjUxNWQ1JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.IO9Dtr3of-5-ieK47GrpazBI1lL3zXDp4PpoRH4sCa0)

3- Since ride_id has no null values, we can utilize it to identify and check for duplicates.

![IMAGE](https://private-user-images.githubusercontent.com/156461228/300295707-b61d322a-3d70-4afb-a2ad-91bcc0ca7a78.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDY0Nzg1NjgsIm5iZiI6MTcwNjQ3ODI2OCwicGF0aCI6Ii8xNTY0NjEyMjgvMzAwMjk1NzA3LWI2MWQzMjJhLTNkNzAtNGFmYi1hMmFkLTkxYmNjMGNhN2E3OC5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwMTI4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDEyOFQyMTQ0MjhaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT00NmNmMTdhYWMxNWQ1YWRjNTBiZTA0NTY4NjdhYWVhMzUwMjQ5MWNiZDVjNTI4MGViNzkyZTlmYjYzYmYzNmI1JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.wOmgP7urYe4kHRIxpum6SoCuTnCI4SYSe_Za7L-G_KM)

 4- The columns started_at and ended_at display the trip's start and end times in the YYYY-MM-DD hh:mm:ss UTC format. To determine the overall trip duration, a new column named ride_length can be generated.


## Data Cleaning

SQL Query[Data Cleaning]( 

1- Rows containing missing values have been removed.

2- Trips with a duration of less than a minute or longer than a day have been excluded.

3- During this step, 1,476,445 rows in total have been removed.


## Analyze and Share

SQL Query[Data Analysis]( 
Data Visualization:

The data has been organized and is now ready for analysis. I performed queries on various pertinent tables and visualized the results using Tableau.
The initial analysis involves comparing member and casual riders, focusing on the types of bikes they use.


![image](https://private-user-images.githubusercontent.com/156461228/300295990-acd30066-0294-4549-a273-e01d91c59308.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDY0Nzg4NDgsIm5iZiI6MTcwNjQ3ODU0OCwicGF0aCI6Ii8xNTY0NjEyMjgvMzAwMjk1OTkwLWFjZDMwMDY2LTAyOTQtNDU0OS1hMjczLWUwMWQ5MWM1OTMwOC5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwMTI4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDEyOFQyMTQ5MDhaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT02ZDJlNjcwMzk2NGI1M2FiYjYxNWM3MDdkMzlhMjJiMTFmMTU1MWM4ZDM1OGYxNjBhZWJiMDc3M2YyMzI3NmI3JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.HBVerdCJOwzzBxG-eJ718gNBCyN8AWDoM-jFg-fGMQE)



More than half (64.53%) of the riders are members, and the rest (35.47%) are casual riders. The percentage charts for each bike type show how much they are used compared to the total. Classic bikes are the most popular, followed by electric bikes. Docked bikes are used the least, mostly by casual riders.


#### Next, we analyze the distribution of trips based on months and days of the week.

![image](https://private-user-images.githubusercontent.com/156461228/300296093-c18edf0a-c2f1-44dc-b379-605c4791caee.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDY0Nzg5NzksIm5iZiI6MTcwNjQ3ODY3OSwicGF0aCI6Ii8xNTY0NjEyMjgvMzAwMjk2MDkzLWMxOGVkZjBhLWMyZjEtNDRkYy1iMzc5LTYwNWM0NzkxY2FlZS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwMTI4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDEyOFQyMTUxMTlaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0yYjRjMjEzOWRjZmU2NmQxMzBiM2I5MGIwOGNiM2Y1OWZkMThjZTViNDQxZGI3YzZlZTQyMjkxZWE4ZWIxM2Q0JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.J_seh3TeM2fFPwls_UuNb5b3oMdXsD7usUMFIhmQP_o)

![image](https://private-user-images.githubusercontent.com/156461228/300296187-e49492f5-e263-42e7-80e5-1f132dae5b28.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDY0NzkwOTEsIm5iZiI6MTcwNjQ3ODc5MSwicGF0aCI6Ii8xNTY0NjEyMjgvMzAwMjk2MTg3LWU0OTQ5MmY1LWUyNjMtNDJlNy04MGU1LTFmMTMyZGFlNWIyOC5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwMTI4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDEyOFQyMTUzMTFaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT01NTdlZWEzNmIyNzI0OGQzMmViZWQxNmY0MjgwOTM5Y2MyYjc0YjYzZGZlZGJmYTZmNjYzODFhMmQzM2I0OGQyJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.VO3mdvoGZ9Nc_lL1k6-1dE1dVJe0ptX74BRdE26ysGc)

### Monthly: In terms of monthly trips, both casual riders and members demonstrate similar trends, with increased trips in spring and summer and reduced activity in winter. The distinction between casual riders and members is minimal, particularly during July in the summer season.


### Weekly: When examining days of the week, it's observed that casual riders increase their trips on weekends, while members, although experiencing a decline over the weekend, still make the most journeys compared to other days of the week.


### Hourly: The data indicates two notable peaks in the number of trips for members: one during the early morning hours (around 6 am to 8 am) and another in the evening (around 4 pm to 8 pm). In contrast, casual riders display a gradual increase in trip numbers throughout the day, peaking in the evening and tapering off later.


From these observations, we can infer that members likely use bikes for commuting to and from work on weekdays, while casual riders prefer bikes consistently throughout the day, with a higher usage frequency on weekends for leisure. Both groups exhibit heightened activity during the summer and spring seasons.
To delve deeper into the distinctions in behavior between casual and member riders, an analysis of the durations of their respective trips can provide valuable insights.
 

## Average Ride Durations Monthly/Weekly/Hourly  in 2023 Trips

![image](https://private-user-images.githubusercontent.com/156461228/300296361-8546dcb0-534a-424e-a0b9-b29f534e6641.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDY0NzkyOTksIm5iZiI6MTcwNjQ3ODk5OSwicGF0aCI6Ii8xNTY0NjEyMjgvMzAwMjk2MzYxLTg1NDZkY2IwLTUzNGEtNDI0ZS1hMGI5LWIyOWY1MzRlNjY0MS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwMTI4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDEyOFQyMTU2MzlaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT03Y2I4ZDU3ZDc1NWYwMzZjYWY4NjNmNDUzMmEzNjNiOTRkN2Y0YjViMjAwMDM1MTU0NGU0NTAzZTBhY2ExZWU4JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.-yEEw4N53Y9kTPwER6Q-Hr7E8lUyK_ANXGkmzegairU)

![image](https://private-user-images.githubusercontent.com/156461228/300296375-a1bdf645-d34a-48e0-9349-52b4017b16d3.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDY0NzkzMTUsIm5iZiI6MTcwNjQ3OTAxNSwicGF0aCI6Ii8xNTY0NjEyMjgvMzAwMjk2Mzc1LWExYmRmNjQ1LWQzNGEtNDhlMC05MzQ5LTUyYjQwMTdiMTZkMy5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwMTI4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDEyOFQyMTU2NTVaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0yMGY4NTBiMmUzZWRiM2MyODhlMzljNWZkOTg1OWFlNzhiOTlmZGUxZmMxN2M3OWQ1YzkzMDc2YTljMzZiZDA2JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.8SgdbgbWxK1xX408mr--Qp-k9DhUps-pCy05t-r8kg4)




It's noteworthy that casual riders, on average, have longer cycling durations compared to members. The average journey length for members remains consistent throughout the year, week, and day. In contrast, casual riders exhibit variations in their cycling durations. They cover greater distances in the spring and summer, on weekends, and between 10 am to 2 pm during the day. Additionally, their trips tend to be brief between five and eight in the morning.

These findings lead to the conclusion that casual commuters cover longer distances (approximately twice as much) but with less frequency compared to members. Their longer journeys on weekends, during the day outside of commuting hours, and in the spring and summer seasons suggest a recreational purpose behind their cycling activities.


To gain a deeper understanding of the distinctions between casual and member riders, an analysis of the starting and ending station locations can provide valuable insights. By applying filters to identify stations with the highest trip frequencies, we can draw conclusions based on the following observations.


## Total Trips Start Locations in 2023

![image](https://private-user-images.githubusercontent.com/156461228/300296497-61ad3098-19b3-4c43-a03d-883b538717af.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDY0Nzk0NTAsIm5iZiI6MTcwNjQ3OTE1MCwicGF0aCI6Ii8xNTY0NjEyMjgvMzAwMjk2NDk3LTYxYWQzMDk4LTE5YjMtNGM0My1hMDNkLTg4M2I1Mzg3MTdhZi5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwMTI4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDEyOFQyMTU5MTBaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1iZDNhZjYzZTVlZTdkMTA0YTg0NDIwOGI2NmM1MjQ2NGQwOTRjMDUzZjZlZWVhZjgwMWQ1YTc5NDhkNjM1NzhlJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.WBRZZ5SJ0TZdAj6cUwtQP7Nr5YW6UMmuBd7vIaQbtJs)



## Total Trips End Locations in 2023

![image](https://private-user-images.githubusercontent.com/156461228/300296511-1ab7c548-6f0f-469a-9a5d-ae7967e8565c.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDY0Nzk0NjgsIm5iZiI6MTcwNjQ3OTE2OCwicGF0aCI6Ii8xNTY0NjEyMjgvMzAwMjk2NTExLTFhYjdjNTQ4LTZmMGYtNDY5YS05YTVkLWFlNzk2N2U4NTY1Yy5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwMTI4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDEyOFQyMTU5MjhaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0xMzcxYjgwNTQ2YWU4YTgzOTQ4NzdhMTk4NzMzZjBiOWU5YTY3YjJmZmM2M2I1YTFmNmE2NzZjNmY5NWY4MjEwJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.DOF8YmAYV7-ydkW8HBqkxOHoeXX9LlbaMWa01eSvsPU)





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













































