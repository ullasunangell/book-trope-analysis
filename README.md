# Book Trope Analysis

## Overview

This project analyses Goodreads book data to explore how narrative themes and book characteristics relate to reader engagement and ratings. The analysis focuses on cleaning the dataset, removing multi-book collection entries, validating page-count quality, and using keyword-based theme detection to examine patterns in reader response.

The project was built in Python using pandas, matplotlib, and seaborn, with analysis conducted in Jupyter Notebook.

## Objectives

- Clean and prepare Goodreads book data for analysis
- Remove collection-style and non-standard records that distort page-count analysis
- Explore summary statistics for page count, ratings, and reader engagement
- Examine the relationship between book length and average rating
- Identify the most popular books based on reader ratings count
- Detect broad narrative themes from book descriptions using keyword matching
- Compare theme frequency and average ratings across detected themes

## Dataset
https://www.kaggle.com/datasets/ayushiiisahu/goodreads-books-dataset
The project uses a Goodreads books dataset sourced from Kaggle. Relevant fields retained for analysis include:

- title
- description
- pages
- publicationDate
- language
- rating
- ratings
- genres

Only columns relevant to the analysis were retained, and records with invalid or non-standard page counts were removed during preprocessing.

## Data Cleaning

Several preprocessing steps were applied to improve data quality:

- Retained only columns relevant to analysis
- Removed books with page counts below 50
- Filtered likely multi-book collections and bundle entries using title-based keyword rules
- Removed slash-separated compilation titles
- Manually excluded a small number of remaining collection-style entries after validation
- Reviewed page-count outliers to confirm that the remaining records were plausible standalone books

After cleaning, the working dataset contained 547 books.

## Analysis

### 1. Summary Statistics
Descriptive statistics were calculated for page count, average rating, and ratings count to understand the distribution of core variables.

### 2. Correlation Analysis
The relationship between page count and average rating was tested using Pearson correlation.

### 3. Popularity Analysis
Books were ranked by total ratings count to identify the most widely read and engaged-with titles in the dataset.

### 4. Theme Detection
Keyword-based theme detection was applied to book descriptions using five broad narrative signals:
- magic
- romance
- murder
- war
- academy

### 5. Theme Presence vs Reader Ratings
Average ratings were compared between books with and without each detected theme.

### 6. Theme Frequency
Detected theme counts were summarised to identify which narrative signals appeared most often across the dataset.

## Key Findings

- After cleaning, page-count outliers were substantially reduced, improving dataset reliability
- The average book length was approximately 335 pages
- Ratings were relatively tightly clustered, with an average rating of 3.87
- Reader engagement was highly skewed, with a small number of books receiving millions of ratings
- Page count had only a weak positive correlation with average rating (0.23)
- Romance was the most frequently detected theme in book descriptions
- Books tagged with war, academy, and magic showed slightly higher average ratings, while murder-tagged books showed slightly lower average ratings
- Theme detection worked as an exploratory proxy rather than a precise classification method

## Tools Used

- Python
- pandas
- Jupyter Notebook
- matplotlib
- seaborn
