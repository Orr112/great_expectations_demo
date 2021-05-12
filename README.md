# great_expectations_demo
Great expectations python library for data testing.


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

![alt text](https://github.com/Orr112/great_expectations_demo/blob/main/ge_data_checks.png)
Image provided by Sam Bail at Superconductive


## Files
- validation_playground.ipynb: this file contains create and insert table queries.
- user_data: this file contains a small amount of data, which is purely for testing purposes.



## Technologies
- Python 3.6
- jupyter


## Libraries 
-great expectations
-pandas


## Install
Use [pip](https://pip.pypa.io/en/stable/)(package manager) to install great_expectations .

```bash
pip intall great_expectations
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
