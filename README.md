
# **Sparkify -** Song Play Analysis

## Introduction
Sparkify's music streaming application is rapidly growing it's user base.  The locally hosted OLAP server is no longer scalable and Sparkify will host the application data on Amazon Web Servics.  The analytics team provided JSON logs which track user activity and JSON metadata which contain data related the songs that are currently available on the application.  The analytics team is particularly interested in understanding what songs users are listening to. 

## Database schema design
The data is stored in a star schema and hosted in the cloud on AWS.  This approach was determined ideal with the following considerations in mind:
- Large data volume
- Fast query aggregation
- Low to moderate level of query complexity
- Moderate level of data integrity is required

## Tables

**Staging tables:** staging_events, staging_events 

**Fact table:** Songplays contains reference links Dimension tables 

**Dimension tables:** users, songs, artists, time

## ETL pipeline

Selected data for **staging_events** was extracted from 2 log_data JSON files and data for **staging_songs** was exxtracted 2 song_data JSON files
Selected data for the **songs**, **users**, **time** and **artists** tables was extracted from **staging_events** and **staging_songs** tables

## Scripts

**sql_queries.py** contents:
- Create and drop database table scripts
- Data import scripts

**create_tables.py** contents:
- Running this script will call sql_queries.py and create tables and content

**etl.py** contents:
- ETL of all datae sets

**Libraries used:**
- configparser
- os
- glob
- psycopg2
- pandas


## Run the following steps in Python3 to repopulate and analyze the data 
1. create_tables.py
2. etl.py
