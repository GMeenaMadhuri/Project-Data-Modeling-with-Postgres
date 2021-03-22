# Project : Data Modeling with postgres

## Project Overview:

<ul>A music streaming platform <strong>Sparkify</strong> wants to analyze the data through their app.Data have been collected on songs and user activity by their streaming app.As they don't have easy way to query their data,they'd like a Data Engineer to create a Postgres database to optimize the queries.So here we are building a database schema and ETL pipeline. For this we need to extract and load the song and log data into a database from the given JSON files.
</ul><br>

## Project Files:
The files in this repository are :
- data/
- etl.py
- etl.ipynb
- sql_queries.py
- create_tables.py
- test.ipynb
- README.md
<br>

**data/** - In this directory we have  two JSON data files.The data is present in subfolders.
- 1. 'log_data/' - It contains JSON files related to songplay log data.

ex:
    {"artist":null,
     "auth":"Logged In",  
     "firstName":"Walter",  
     "gender":"M",  
     "itemInSession":0,
     "lastName":"Frye",
     "length":null,
     "level":"free",  
     "location":"San Francisco-Oakland-Hayward, CA",  
     "method":"GET",  
     "page":"Home",
     "registration":1540919166796.0,  
     "sessionId":38,  
     "song":null,
     "status":200,  
     "ts":1541105830796,  <br>
     "userAgent":"\"Mozilla\/5.0 (Macintosh; Intel Mac OS X 10_9_4) AppleWebKit\/537.36 (KHTML, like Gecko) Chrome\/36.0.1985.143 Safari\/537.36\"",  <br>
     "userId":"39"
     }
- 2. 'song_data/' - It has JSON files that contains metadata about song and artist of that song.

ex: 
    {"num_songs": 1,<br>
     "artist_id": "ARJIE2Y1187B994AB7",<br>
     "artist_latitude": null, <br>
     "artist_longitude": null,<br>
      "artist_location": "",<br>
      "artist_name": "Line Renaud",<br>
      "song_id": "SOUPIRU12A6D4FA1E1", <br>
      "title": "Der Kleine Dompfaff",<br>
      "duration": 152.92036, <br>
      "year": 0}

**etl.py** -<ul> This script reads and processes the files from song and log data and loads into database tables.It has detailed instructions on the ETL process.</ul>

**etl.ipynb** - <ul>This a Jupyter notebook used to test the etl functions before adding them to '_etl.py_' file.</ul>

**sql_queries.py** - <ul>This script contains all the SQL commands used to create , drop and insert  values into the tables.</ul>

**create_tables.py** - <ul>This script is used to connect to 'Sparkify' database and execute the commands which we have written in '_sql_queries.py_'.We need to run this file each time before you run the ETL scripts to reset the tables.</ul>

**README.md** - <ul>It provides details information about the project.</ul>

<br>

## Sparkify DataSchema :
The DataSchema has 5 tables represented in a Star schema.

#### Fact Table -
- songplays - It has records in log data associated with song plays.  

#### Dimension Tables -
- users - It has data about the users in the app.
- songs - It has data about the songs in music database.
- artists - It has data about the artists in music database.
- time - It has data about the timestamps of records in songplays broken down into specific units.



## Project Steps :
#### Step1 :-
<ul>We need to write create ,drop and insert statements for each table in <em>'sql_queries.py'</em> file.</ul>

#### Step2 :-
<ul>Run the <em>'create_tables.py'</em> to create the Sparkify database and related tables.</ul>
- !python create_tables.py

#### Step3 :-
<ul>Run the <em>'test.ipynb'</em> notebook file to confirm the creation of the tables with valid columns.</ul>
- Note:"Restart Kernal" to close the connection to database everytime after running this file.

#### Step4 :-
<ul>This step is for building ETL Processes.Here we need to develop ETL processes for each table with the help of instructions given in <em>'etl.ipynb'</em> notebook.Make sure to run the <em>'test.ipynb'</em> to confirm that records are inserted into table and rerun the <em>'create_tables.py'</em> before to reset the tables.
</ul>

#### Step5 :-
<ul>Here we are building the ETL pipeline.The <em>'etl.ipynb'</em> contains the ETL pipeline processes to populate the <em>songs</em> and <em>artists</em> tables from the data within the JSON song files <em>(`data/song_data/`)</em> and to populate the <em>users</em> and <em>time</em> tables from the JSON log files. So with the help <em>'etl.ipynb'</em> notebook, need to complete the <em>'etl.py'</em> file which process the entire datasets.

- !python etl.py
- And also make sure to run the <em>'test.ipynb'</em> to confirm that records are inserted into table and rerun the <em>'create_tables.py'</em> before, to reset the tables.
    <ul>
