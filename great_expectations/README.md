# great_expectations_demo
Great expectations python library


## Table of contents
* [Intro](#Intro)
* [Motivation](#Motivation)
* [Files](#Files)
* [Technologies](#Technologies)
* [Libraries](#Libraries)
* [Install](#Install)
* [Analysis](#Analysis)
* [Acknowledgement](#Acknowledgement)

## Intro
Great expectations is a python library used for automating unit testing of data.  Data scientists and engineers can use the great expectations libary to maintian data quality by validating, documenting, and profiling their data.  

A visual summation of the great expectations library:
![alt text](https://docs.greatexpectations.io/en/stable/_images/ge_overview.png)
Image provide by Great Expectations website. 



## Motivation
A good rule of thumb for an ETL process is to test data at any point within a data pipeline in which data is handed off from one component of the pipeline to another component. Great expectations provides the ability to test at those various points along the data pipeline by providing a user friendly juypter notebook in which teams can set expectations for their data.  The team at great expectations provides a visulization of how these data checks could be implemented into a data pipeline:

![alt text]()
Image provided by Sam Bail at Superconductive


## Files
- sql.py: this file contains create and insert table queries.
- create_tables.py: this file connects to the database, drops old tables and then creates ables from sql.py file.
- etl.py: this file extracts data from song and log files, transforms the data, and then loads the data into tables.
- test.ipynb: this notebook is used to perform basic data checks on data inserted into the tables.
- basicStats.ipynb: used to draw some basic user and song analysis. 


## Technologies
- Python 3.6
- jupyter
- SQL

## Libraries 
-psycopg2
-pandas
-glob
-os

## Install
Use [pip](https://pip.pypa.io/en/stable/)(package manager) to install psycopg2 and pandas.

```bash
pip intall psycopg2
pip install pandas
```
glob and os come pre-installed as they are part of python standard library.


## Analysis 

### Demogoraphics
```
--Total Users
select count(*) from users

--Percentage Users in Paid Level
Select (count(*)*100) / 84  AS PercentPaidLevel from users where level = 'paid'

--Percent Paid User by Identified Gender
Select (count(*)*100) / 84  AS PercentFemalePaidLevel from users where gender = 'F' and level = 'paid'

Select (count(*)*100) / 84  AS PercentMale from users where gender = 'M' and level = 'paid'

--User Gender Breakdown
Select (count(*)*100) / 84  AS PercentMale from users where gender = 'M'

Select (count(*)*100) / 84  AS PercentFemale from users where gender = 'F'

```
### Artist/Song Analysis
```
--Max Song Length
select (max(duration))/60 AS MaxSongLength from songs 

--Percentage Song Longer than Average
Select (count(*)*100)/72 AS PercentSongsGtAverage from artists a Join songs s on a.artist_id = s.artist_id  where duration >= 219

```

## Acknowledgement
- Facts and Dimensions Table layout above provide by ZenTut.
- This project was peformed as part of the Udacity Data Engineering Nanodegree Program.
