# Data Modeling with Cassandra Project Sparkify Apache Cassandra ETL:
## Project Introduction:
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analysis team is particularly interested in understanding what songs users are listening to. Currently, there is no easy way to query the data to generate the results, since the data reside in a directory of CSV files on user activity on the app.

My role is to create a database schema and ETL pipeline for this analysis.
## Prerequisites:
This project makes the folowing assumptions:
- Python 3 installed,Python 3 Libraries available are given below:
    - pandas.
    - cassandra.
    - re.
    - os.
    - glob.
    - json.
    - numpy.
    - csv.
- A cassandra instance is available on local machine.
- Jupyter Notebook is available.
## Dataset:
For this project, we shall be working with one dataset:  `event_data`. The directory of CSV files partitioned by date. Here are examples of filepaths to two files in the dataset:

```
event_data/2018-11-08-events.csv
event_data/2018-11-09-events.csv
```
## Schema:

This  project creates an Apache Cassandra keyspace  `sparkifyks`  for a music app,  _Sparkify_. The purpose of the NoSQL database is to answer queries on song play data. The data model includes a table for each of the following queries:

1.  Getting the artist, song title and song's length in the music app history that was heard during sessionId = 338, and itemInSession = 4
    
2.  Getting only the name of artist, song (sorted by itemInSession) and user (first and last name) for userid = 10, sessionid = 182
    
3.  Getting every user name (first and last) in my music app history who listened to the song 'All Hands Against His Own'.

The 3 tables in the model are named as follows

1.  **`session_library`**  includes artist, song title and song length information for a given  `session_id`  and  `item_in_session`.
    
2.  **`user_library`**  includes artist, song and user for a given  `user_id`  and  `session_id`.
    
3.  **`song_library`**  includes user names for a given song.
## Project Template:
-  **event_data**  folder nested at the home of the project, where all needed data reside.
-  **Project_1B_ Project_Template.ipynb**  the code itself.
-  **event_datafile_new.csv**  a smaller event data csv file that will be used to insert data into the Apache Cassandra tables.
-  **images**  a screenshot of what the denormalized data should appear like in the event_datafile_new.csv.
-  **README.md**  current file, provides discussion on my project.
## Steps Followed:
1.  I designed tables to answer the queries outlined in the project template.
2.  I wrote Apache Cassandra  `CREATE KEYSPACE`  and  `SET KEYSPACE`  statements.
3. I developed your  `CREATE`  statement for each of the tables to address each question.
4. I loaded the data with  `INSERT`  statement for each of the tables.
5. I included  `DROP TABLE`  statement for each table, this way I could run drop and create tables whenever i want to reset my database and test my ETL pipeline.
6.  I tested my results by running the proper select statements with the correct  `WHERE`  clause.
