# Song Play Analysis

## How to run
- python create_tables.py
- python etl.py

## Purpose
A fictional startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Their data resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

The scripts below create a Postgres database with tables designed to optimize queries on song play analysis.

## Schema
Using the song and log datasets, the scripts create a star schema optimized for queries on song play analysis. This includes the tables below.

### Fact Table
- songplays - records in log data associated with song plays i.e. records with page NextSong:
songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent

### Dimension Tables
- users - users in the app:
user_id, first_name, last_name, gender, level
- songs - songs in music database:
song_id, title, artist_id, year, duration
- artists - artists in music database:
artist_id, name, location, lattitude, longitude
- time - timestamps of records in songplays broken down into specific units:
start_time, hour, day, week, month, year, weekday

## Files
In addition to the data files, the project workspace includes six files:

- test.ipynb displays the first few rows of each table to let you check your database.
- create_tables.py drops and creates your tables. This script resets your tables. Run this each time you run the ETL scripts.
- etl.ipynb reads and processes a single file from song_data and log_data and loads the data into the tables. This notebook contains detailed instructions on the ETL process for each of the tables.
- etl.py reads and processes files from song_data and log_data and loads them into the tables.
- sql_queries.py contains all the sql queries, and is imported into the last three files above.
