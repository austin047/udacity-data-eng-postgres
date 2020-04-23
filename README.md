## Data Modeling for Sparkify.
***

### Problem
Sparkify needs to do analysis on the song and user activity on their music streaming app for unserstanding what songs users are listening to.
### Purpose
Given songs and user activity data, Use Data Modeling to create a database with tables optimized for song play **analysis** and ETL pipeline.


### Goals Achieved
For the Pupose of this project 4 dimension tables were created: *users, songs, artists* and *time* linked to 1 facts table *songplays* to form a star schema that will allow for easy analysis.

Analytical queries can now be performed on the facts table songplays to answer questions like "How many".

ELT Pipeline were also created for running queries on the data provided from **log** and **song**  data sets for songs and user activity.



### Sample Queries
A sample query that can be performed for song play anylysis.

1. How many users from 'Chicago-Naperville-Elgin, IL-IN-WI' listen to Elena's Songs.

##### Query
`SELECT COUNT(*) FROM songplays JOIN artists ON songplays.artist_id=artists.artist_id WHERE songplays.location='Chicago-Naperville-Elgin, IL-IN-WI' AND artists.name = 'Elena''`

 **Result** : 1


2. How many users from 'Lake Havasu City-Kingman, AZ' listen to song with title 'City Slickers'

##### Query
`SELECT COUNT(*) FROM songplays JOIN songs ON songplays.song_id = songs.song_id  WHERE location = 'Tampa-St. Petersburg-Clearwater, FL' AND title = 'City Slickers'`

 **Result** : 0
