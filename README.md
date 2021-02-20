# Movies ETL

Creation of a cleaned dataset that could then be used to predict low-budget movie popularity

## Overview of the Analysis

The aim of this project is to create a data set that would be used by a streaming company to develop an algorithm to predict which low budget movies being released will become popular. This would ultimately allow the company to pick up streaming rights for these movies at a bargain price. The task involves scraping movie data from Wikipedia (for all movies released since 1990), and rating data from the website MovieLens, to combine into one clean dataset that could then be used by analysts. 

ETL process: 

*Extract Wikipedia and Kaggle data fromn their respective files
*Transform the data sets by cleaning them up and joining them together
*Load the cleaned dataset into a SQL database

## Resources

Software: Python 3.7.9, Jupyter Notebook 6.1.4, Anaconda 1.10.0, PostgreSQL 11.10.2, pgAdmin 4.29

## Results

### ETL Function Written to Read Three Data Files

An [ETL function]() was first tested by refactoring code in order to read in the three data files. From this, the function converted the Wikipedia JSON, Kaggle metadata, and MovieLens ratings data into Pandas DataFrames. 

![]()

Figure 1. Wikipedia movies DataFrame head

![]()

Figure 2. Kaggle metadata DataFrame head

![]()

Figure 3. MovieLens ratings DataFrame head

### Extraction and Tranformation of Wikipedia Data

Using the [ETL process and refactoring](), the Wikipedia data was extracted and tranformed so the cleaned data could be merged with the Kaggle metadata. 

![]()

Figure 4. Transformed Wikipedia DataFrame head

![]()

Figure 5. Transformed Wikipedia DataFrame retained collumns

### Extraction and Transformation of Kaggle Data

After this, the Kaggle metadata and MovieLens rating data was [extracted and transformed]() into seperate DataFrames before merging them, then also merging with the Wikipedia DataFrame.

![]()

Figure 6. Combined DataFrame for cleaned kaggle and ratings data

![]()

Figure 7. Combined, cleaned DataFrame for all three datasets

### Creation of the Movie Database

The final task was to add the extracted and tranformed data into a SQL database. Both the combined movies and the rating data were [loaded]() into PostgreSQL as tables.

![]()

Figure 8. SQL query for the movies table

![]()

Figure 9. SQL query for the ratings table