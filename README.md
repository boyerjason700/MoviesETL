<p align="center">
  <img width="560" height="300" src="https://user-images.githubusercontent.com/74840026/129463848-c1f38fe3-8a1a-4094-b29a-f40178e10d81.PNG">
</p>

# Movies-Extract, Transform, Load

# Overview
Create an ETL pipeline from raw data to a SQL database.  

Amazing Prime wants to develop an algorithm to predict which low budget movies will become popular so they can buy the streaming rights for those movies.  To have some fun and connect with the local coding community, Amazing Prime is sponsoring a hackathon where the goal is to create their prediction algorithm using a clean database of movies which we will create.  We are tasked with automating the ETL process by creating one function to extract multiple data sets from Wikipedia and Kaggle, transform the data sets and clean out any null or unwanted data and then combine these data sets into a workable form and load them into a SQL database for the hackathon participants to use.

# Resources
Wikipedia Movie Dataset
  - wikipedia-movies.json 

[Kaggle-The Movie Data Set](https://www.kaggle.com/rounakbanik/the-movies-dataset)
  - movies_metadata.csv 
  - ratings.csv
# Process
## 1. Extract
Using the wikipedia-movies.json, movies_metadata.csv and ratings.csv files, we begin by loading each into our Juypter notebook to verify the data looks good by performing various checks( `.head(), .tail(), .sample()` ) to make sure the data is in the proper format and not corrupted.

<p align="center">
  <img width="560" height="300" src="https://user-images.githubusercontent.com/74840026/129465153-2aa76c4e-7612-42ba-8028-347047fc82a3.PNG">
</p>

## 2. Transform
Inspecting our data, we can identify where problems occur.  Once we have identified the problems, we can develop a plan and make sure it is worth the time to fix.  Once we have our plan, we can then execute it.

<p align="center">
  <img width="560" height="300" src="https://user-images.githubusercontent.com/74840026/129465161-71bbae32-9c06-4b90-a5f6-6281ffdb9db2.PNG">
</p>

  ### Problems encountered
   - entries with missing of null values
   - removing un-needed and duplicate columns
   - renaming columns for better understanding
   - converting data types using regular expressions (text to numeric, dates, Booleans)
   
<p align="center">
  <img width="860" height="200" src="https://user-images.githubusercontent.com/74840026/129465166-1ba42440-5e9e-468f-b82c-c4e04c850d95.PNG">
</p>

  ### Merging DataFrames
  We found both data sets contained the same categories for multiple columns.  Before merging, we used our 'Inspect, Plan, Execute' method to identify which set would be more  useful to include and how to fill in missing data.

<p align="center">
  <img width="860" height="300" src="https://user-images.githubusercontent.com/74840026/129465168-1c0bd502-90ff-4437-bde5-d691e85282a4.PNG">
</p>

## 3. Load
Using the `to_sql` method, we connected Python to PostgreSQL to import our DataFrames and create workable databases for the hackathon participants to use. 

<p align="center">
  <img width="860" height="350" src="https://user-images.githubusercontent.com/74840026/129465169-41efccc5-48e3-4b88-af53-0ef4eb56751c.PNG">
</p>
