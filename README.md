
# Sparkify - Data Modeling with Postgres
Sparkify - Data Modeling with Postgres - Udacity Data Engineering Expert Track.

In this project, I built an ETL pipeline using Python, created a Postgres database that contains fact and dimension tables for a star schema for a particular analytic focus (analyze Sparkify's collected data on songs and user activity on their new music streaming app), and wrote an ETL pipeline that transfers data from JSON files in two local directories into these tables in Postgres using Python and SQL.

## Project Datasets:

- Songs Dataset:

  This dataset is a subset of real data from the [Million Song Dataset](http://millionsongdataset.com/). Each file is in JSON format and contains metadata about a song and the artist of that song. The files are partitioned by the first three letters of each song's track ID.
- Log Dataset:

  This dataset consists of log files in JSON format generated by this [event simulator](https://github.com/Interana/eventsim) based on the songs in the dataset above. These simulate activity logs from a music streaming app based on specified configurations. The files are partitioned by year and month.

![log-data](https://user-images.githubusercontent.com/46838441/191114096-960d74b7-2745-4006-bef7-b5f616e1113f.png)


## Project Files:

- ```test.ipynb``` displays the first few rows of each table to check the database.
- ```create_tables.py```drops and creates the database and its tables.
- ```etl.ipynb``` reads and processes a single file from song_data and log_data and loads the data the tables.
- ```etl.py``` reads and processes files from song_data and log_data and loads them into the tables.
- ```sql_queries.py``` contains all sql queries.

## Project Details:

The project purpose is analyze the Sparkify collected data on songs and user activity on their new music streaming app, to understand what songs users are listening to, by creating a Postgres database with tables designed to optimize queries on song play analysis.

For this analysis; I created a database schema and ETL pipeline. then tested the database and ETL pipeline by running given queries by the analytics team from Sparkify and compare the results with their expected results.

A star schema optimized for queries on song play analysis. It was created using the song and log datasets, and it includes the following tables:

- Fact Table
  - ```songplays``` records in log data associated with song plays i.e. records with page 'NextSong'
    - songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent.
- Dimension Tables
  - ```users``` users in the app
    - user_id, first_name, last_name, gender, level
  - ```songs``` songs in music database
    - song_id, title, artist_id, year, duration
  - ```artists``` artists in music database
    - artist_id, name, location, latitude, longitude
  - ```time``` timestamps of records in songplays broken down into specific units
    - start_time, hour, day, week, month, year, weekday

## Tools and Technologies:
- Python 3.
- Pandas, NumPy, Psycopg2 Python Libraries.
- ETL: Extract, Transform, Load Data
- Data Warehouse concepts.
- SQL.
- Jupyter Notebook.
- PostgreSQL server.

## Project Steps:
- 1- Planing for the database schema.
- 2- Write the SQL queries: create, drop, and select statments.
- 3- Create the Postgres database.
- 4- Develop the ETL processes for each table.
- 5- Build the ETL pipelines.
- 6- Test the results.

## How To Run The Project?

- 1- Install Python 3.
- 2- Install PostgreSQL
- 3- Download the scripts and the datasets.
- 4- Run ```create_tables.py`` file to create the database and its tables.
- 5- Run ```etl.py``` to load the data into the database tables.
- 6- Run ```test.ipynb``` to view the results.

## Screnshots:

  ### Artists Table:
  
  ![image](https://user-images.githubusercontent.com/46838441/191114300-5c7a8ac1-df6a-4ba6-9d9b-51d559ceccaa.png)

  ### Songs Table:
  
  ![image](https://user-images.githubusercontent.com/46838441/191114455-ccfb6ff6-b83d-4628-8918-560c6289c854.png)
  
  ### Time Table:
  
  ![image](https://user-images.githubusercontent.com/46838441/191114558-93183015-7970-4e5b-ab00-db67bda96868.png)


  ### Users Table:
  
  ![image](https://user-images.githubusercontent.com/46838441/191114680-d4d41162-b2fa-4f93-8736-df742345353f.png)

  ### Songplays Table:
  
  ![image](https://user-images.githubusercontent.com/46838441/191114816-f0304613-4c42-49b4-86db-c4a62fd5c72b.png)
