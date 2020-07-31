# Objective
A startup called Sparkify owns a music streaming app and  wants to know what songs users are listening to based on data collected on songs and user activity on their app. Currently since all the data resides in a directory of JSON logs, there isn't a way to query that data to get actionable insights that would help the business. Due to this we performed some Data Modeling, creating a postgres database and built an ETL pipeline using Python to load the data from the json files to the tabels in the database. In other to create those tables the data mart schema we adopted was the star schema which involves structing the data into facts and dimensions. This data mart was used due to its simplicity and the fact that we can clearly see the measurements, metrics or facts of the business as well as the categorization of those facts and users. 
 

# Datasets
Song Dataset-contains metadata about a song and the artist of that song
Log Dataset-contains activity logs from a music streaming app based on specified configurations


# Fact Table
songplays - records in log data associated with song plays i.e. records with page NextSong
-->songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent

# Dimension Tables
users - users in the app
-->user_id, first_name, last_name, gender, level

songs - songs in music database
-->song_id, title, artist_id, year, duration

artists - artists in music database
-->artist_id, name, location, latitude, longitude

time - timestamps of records in songplays broken down into specific units
-->start_time, hour, day, week, month, year, weekday

![](schema.png)

# Files in Repository
data- directory of JSON files containing song and log datasets 
test.ipynb- run to check few rows of each table to confirm correct data inserted to database
create_tables.py- run to drop and create your tables. Used to reset table before running ETL scripts.
etl.ipynb- reads and processes a single file from song_data and log_data and loads the data into your tables. 
etl.py- reads and processes files from song_data and log_data and loads them into your tables. 
sql_queries.py- contains all your sql queries
README.md- Project Documentation

# How to run this Project
-Make sure all files are in a single location
-run create_tables.py
-run etl.py

