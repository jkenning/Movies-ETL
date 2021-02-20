# Movies ETL

Creation of a cleaned dataset that could then be used to predict low-budget movie popularity

## Overview of the Analysis

The aim of this project is to create a data set that would be used by a streaming company to develop an algorithm to predict which low budget movies being released will become popular. This would ultimately allow the company to pick up streaming rights for these movies at a bargain price. The task involves scraping movie data from Wikipedia (for all movies released since 1990), and rating data from the website MovieLens, to combine into one clean dataset that could then be used by analysts. 

ETL process: 

* Extract Wikipedia and Kaggle data fromn their respective files

* Transform the data sets by cleaning them up and joining them together

* Load the cleaned dataset into a SQL database

## Resources

Data: [Wikipedia-movies.json](https://github.com/jkenning/Movies-ETL/blob/main/Resources/wikipedia-movies_.json), [movies_metadata.csv](https://github.com/jkenning/Movies-ETL/blob/main/Resources/movies_metadata_.csv), [ratings.csv](https://github.com/jkenning/Movies-ETL/blob/main/Resources/ratings_.csv)

Software: Python 3.7.9, Jupyter Notebook 6.1.4, Anaconda 1.10.0, PostgreSQL 11.10.2, pgAdmin 4.29

## Results

### ETL Function Written to Read Three Data Files

An [ETL function](https://github.com/jkenning/Movies-ETL/blob/main/ETL_function_test.ipynb) was first tested by refactoring code in order to read in the three data files. From this, the function converted the Wikipedia JSON, Kaggle metadata, and MovieLens ratings data into Pandas DataFrames. 

![](https://github.com/jkenning/Movies-ETL/blob/main/Resources/wikipedia_df.png)

Figure 1. Wikipedia movies DataFrame header

![](https://github.com/jkenning/Movies-ETL/blob/main/Resources/kaggle_df.png)

Figure 2. Kaggle metadata DataFrame header

![](https://github.com/jkenning/Movies-ETL/blob/main/Resources/ratings_df.png)

Figure 3. MovieLens ratings DataFrame header

### Extraction and Tranformation of Wikipedia Data

Using the [ETL process and refactoring](https://github.com/jkenning/Movies-ETL/blob/main/ETL_clean_wiki_movies.ipynb), the Wikipedia data was extracted and tranformed so the cleaned data could be merged with the Kaggle metadata. 

![](https://github.com/jkenning/Movies-ETL/blob/main/Resources/transformed_wikipedia_df.png)

Figure 4. Transformed Wikipedia DataFrame header

![](https://github.com/jkenning/Movies-ETL/blob/main/Resources/transformed_wikipedia_df_collumns.png)

Figure 5. Transformed Wikipedia DataFrame retained collumns

### Extraction and Transformation of Kaggle Data

After this, the Kaggle metadata and MovieLens rating data was [extracted and transformed](https://github.com/jkenning/Movies-ETL/blob/main/ETL_clean_kaggle_data.ipynb) into seperate DataFrames before merging them, then also merging with the Wikipedia DataFrame.

![](https://github.com/jkenning/Movies-ETL/blob/main/Resources/movies_with_ratings_df.png)

Figure 6. Combined DataFrame for cleaned kaggle and ratings data

![](https://github.com/jkenning/Movies-ETL/blob/main/Resources/combined_movies_df.png)

Figure 7. Combined, cleaned DataFrame for all three datasets

### Creation of the Movie Database

The final task was to add the extracted and tranformed data into a SQL database. Both the combined movies and the rating data were [loaded](https://github.com/jkenning/Movies-ETL/blob/main/ETL_create_kaggle_database.ipynb) into PostgreSQL as tables.

![](https://github.com/jkenning/Movies-ETL/blob/main/Resources/movies_query.png)

Figure 8. SQL query for the movies table

![](https://github.com/jkenning/Movies-ETL/blob/main/Resources/ratings_query.png)

Figure 9. SQL query for the ratings table
