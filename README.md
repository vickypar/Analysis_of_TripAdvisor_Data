# Analysis_of_TripAdvisor_Data
This project regards extraction of textual data from TripAdvisor reviews and their preprocessing and analysis in order to find out useful insights. More specifically, the reviews in TripAdvisor for restaurants in Thessaloniki are scraped using Selenium. Also, they are analyzed using Python in order to create interesting visualizations and a sentiment analysis is conducted to extract the sentiment of the reviews. Finally, a classifier is trained to predict the gender and the age group of the reviewer based on the text of the review.

## Table of Contents

[0. Installation](https://github.com/vickypar/Analysis_of_TripAdvisor_Data#0-installation)

[1. About](https://github.com/vickypar/Analysis_of_TripAdvisor_Data#1-about)

[2. Web Scraping Process](https://github.com/vickypar/Analysis_of_TripAdvisor_Data#2-web-scraping-process)

[3. Data Analysis](https://github.com/vickypar/Analysis_of_TripAdvisor_Data#3-data-analysis)

[4. Sentiment Analysis](https://github.com/vickypar/Analysis_of_TripAdvisor_Data#4-sentiment-analysis)

[5. User Profiling](https://github.com/vickypar/Analysis_of_TripAdvisor_Data#5-user-profiling)


## 0. Installation 

The code requires Python and Selenium.

## 1. About

**Analysis of TripAdvisor Data** is a project that was created as a semester Project in the context of “Web Mining” class.
MSc Data and Web Science, School of Informatics, Aristotle University of Thessaloniki.

## 2. Web Scraping Process

The information that we want to scrape from each restaurant review using Selenium with chromedriver is the following:
- Username of the reviewer
- Age of the reviewer
- Gender of the reviewer
- Location of the reviewer
- Review distribution of the reviewer
- Name of the business
- Review date
- Visit date of the reviewer
- Title of the review
- Text of the review
- Rating of the review

![image](https://user-images.githubusercontent.com/95586847/180650940-99ea59bc-c78c-481f-aed4-f7e588224148.png)

The process followed to scrape the data is described below:
- Find the way TripAdvisor is set up using F12
- Collect the restaurant links
- Collect the important elements of each review 

  Review             |  Reviewer
  :-------------------------:|:-------------------------:
  ![image](https://user-images.githubusercontent.com/95586847/180652283-ba69e0e6-3c01-49c2-81db-d2d46033b270.png)  |  ![image](https://user-images.githubusercontent.com/95586847/180652293-143ed578-2415-47ed-8fff-808f309675f5.png)

The whole scraping process took around 15 hours for 14373 reviews.

## 3. Data Analysis

### 3.1 Preprocessing 
- Drop unwanted columns
- Process "Review" column
  - Remove punctuation marks
  - Lowercase
  - Tokenize (split each review into words)
  - Remove stopwords
  - Stemming (produce morphological variants of a root word)
- Process "Rating_Date" column
  - Extract review's month 
  - Extract review's year

Final format:
![image](https://user-images.githubusercontent.com/95586847/180653391-b4747f1d-81be-4308-8d02-c5ac59e003fc.png)

### 3.2 Monthly Reviews
Visualize the monthly number of reviews:

<center><img src="https://user-images.githubusercontent.com/95586847/180653719-ea37a8a2-03c2-48cf-852a-a72c1dd39e2a.png" width="500"></center>

The month with the most reviews made is August with September trailing right behind. This is due to the tourism Thessaloniki gets late at summer.
Despite the peak observed during summer, September and October, we can see that the
number of monthly reviews remains the same during the rest of the months.

### 3.3 Most Common Words, Bi-grams, Tri-grams
### 3.4 Fastest Growing and Fastest Shrinking Words
### 3.5 Topic Modeling 
### 3.6 Map of Locations


## 4. Sentiment Analysis 

### 4.1 Polarity Score
### 4.2 Most Common Words in Positive and Negative Reviews 
### 4.3 Polarity Score per Restaurant 

## 5. User Profiling

### 5.1 Gender
### 5.2 Age Group

