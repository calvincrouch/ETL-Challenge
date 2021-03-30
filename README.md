ETL Project
03/27/2021
GROUP 3: Alex Zapuchlak, Brian Halvorson , Calvin Crouch

# MOVIE PLOTS
![GitHub Logo](/images/wiz.jpg)

## Objective
Read, clean, and consolidate dataset files by method of ETL (Extract, Transform, and Load) using Python in Jupyter Notebook and SQL in pgAdmin. 

## Method
We have decided to examine and combine two CSV files we resourced from Kaggle.com. These CSV files include the “Netflix Movies and TV Shows” dataset and the “Wikipedia Movie Plots” dataset, in which we aim to add in movie plot descriptions for the current listing of Netflix movies.

## Instructions
1. ### Extract
    1. In Jupyter notebook load, read and define dataframes from netflix movie csv (https://www.kaggle.com/shivamb/netflix-shows) and wikipedia movie plot csv (https://www.kaggle.com/jrobischon/wikipedia-movie-plots).

1. ### Transform
    1. ##### Netflix Dataset
        1. Filter the "type" column to only show data that has Movie as the value string and not TV Show as the value.
        1. Filter the dataframe to only show the columns "title", "country", "release_year", and "listed_in"
        1. Change the name of the "listed_in" column to "genre".
        1. Filter the dataframe to only include data where the "release_year" has a value >= 2010 and <=2017.  
    1. ##### Wiki Dataset
        1. Check for missing "Plot" column entries by performing a .dropna.
        1. Filter the dataframe to only include the columnts "Title", "Release Year", "Director", "Genre", "Plot".
        1. Change the names of the columns to "title", "release_year", "director", "genre", and "plot".
        1. Filter the dataframe to only include data where the "release_year" has a value >= 2010 and <=2017.
        1. Perform a drop duplicates for any duplicate movies.

1. ### SQL
    1. Create new database in pgAdmin 
    1. Build the schema
    1. Query Tool
        1. Create Netflix Table
            1. title: Primary Key 
            1. country: TEXT
            1. release_year: INT
            1. genre: TEXT
        1. Create Wiki Table
            1. title: Primary Key
            1. release_year: INT
            1. director: TEXT
            1. genre: TEXT
            1. plot: TEXT
    
1. ### Load
    1. Create config.py text file in Jupyter Notebook to store your password.
    1. Add the config.py to your git.ignore
    1. Connect the local database with connection string.
    1. Connect to the engine.
    1. Use Pandas to plug in the Netflix CSV file data into the SQL database
    1. Use Pandas to plug in the Wiki CSV file data into the SQL database 
    1. Confirm Netflix Data has been added by running a query
    1. Confirm Wiki Data has been added by running a query
