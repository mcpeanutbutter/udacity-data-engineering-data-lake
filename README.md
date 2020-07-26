# Project summary

## Project description
In this project, a extraction-transfer-load pipeline for a data lake is built using Spark. Again, this project is quite similar to the previous projects, with the main difference in this case being in the utilization of a spark cluster. In total, five tables should be created and populated using data from two different S3 sources:

1. songplays, a fact table listing who played which song by which artist at what time, extracted from log data
2. users, a dimension table containing user information like name and level, extracted from log data
3. songs, a dimension table containing song information like title and length, extracted from song data
4. artists, a dimension table containing artist information like name and location, extracted from song data
5. time, a dimension table that lists the units of time (hours, minutes etc.) for each timestamp in the fact table, extracted from log data

## Project files and running the project
The relevant file for submission is `etl.py`. Given the presense of a suitable spark installation, it can be executed from the cli via:
```
python etl.py
```
Unfortunately, the environment that was provided kept throwing 403 errors when trying to read from S3. Therefore, the script was developed and tested on Amazon EMR could *not* be tested in the udacity enviroment. 

## Structure of etl.py
There are two relevant functions in `etl.py`, `process_song_data()` and `process_log_data()`. These functions perform operations that were done with SQL queries in previous exercises:
* Extract song and artist information from song data
* Extract user, time and songplay information from log data. The latter requires a join with song_data in order to make the fields `song_id` and `artist_id` available in the songplay data.

## Attributions
The following solutions were used as guidance:
* **[bondxue](https://github.com/bondxue/Data-Lake-with-Spark)**
* **[jonathankamau](https://github.com/jonathankamau/udacity-data-lake-project)**
