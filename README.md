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
The library "WordCloud" was used to visualize unigrams, bigrams and trigrams that occur frequently at 1-star and 5-star reviews.
- Unigrams
  1-star             |  5-star
  :-------------------------:|:-------------------------:
  ![image](https://user-images.githubusercontent.com/95586847/180654770-2e3d2e93-3cbd-434a-9526-45448c80112b.png) |  ![image](https://user-images.githubusercontent.com/95586847/180654828-091083c3-afd0-4b14-a175-e4198324fbbc.png)

- Bigrams
  1-star             |  5-star
  :-------------------------:|:-------------------------:
  ![image](https://user-images.githubusercontent.com/95586847/180654787-87f3e4c9-e06d-46c0-b405-0371010302d0.png)  |  ![image](https://user-images.githubusercontent.com/95586847/180654838-f1e737cc-96cf-4078-bcb9-74ac53c166b2.png)


- Trigrams
  1-star             |  5-star
  :-------------------------:|:-------------------------:
  ![image](https://user-images.githubusercontent.com/95586847/180654801-6c14bc94-01d9-44cf-aa1a-0da743b3d19f.png) |  ![image](https://user-images.githubusercontent.com/95586847/180654854-d6f4367a-6ed4-412d-985e-fb241caa2a47.png)

It is obvious that the bigger the "n" gets, the better it describes the general feeling of a review.
Unigrams are just common words, while some of the bigrams and most of the trigrams give a
more complete view of the context. 

### 3.4 Fastest Growing and Fastest Shrinking Words
Another interesting visualization would be to explore the fastest growing and shrinking words
across the time.
For instance:
"Vegan"            |  "Soutzoukakia"
:-------------------------:|:-------------------------:
![image](https://user-images.githubusercontent.com/95586847/180656507-006479a8-d13c-4b06-ae92-47894bdcbbf7.png) |  ![image](https://user-images.githubusercontent.com/95586847/180656524-9da3fc25-21f2-4542-bbf2-b7a4670cc424.png)

### 3.5 Topic Modeling 
We try to extract and visualize emerging topics from all the reviews across time using Latent Dirichlet Allocation (LDA) algorithm. We split the reviews in chronological order and find the four most representative topics.
![image](https://user-images.githubusercontent.com/95586847/180656871-24bb1cd1-c18c-4c55-9c6d-58150495b3d8.png)

### 3.6 Map of Locations
We also visualize in a map the location of reviewers so that we can make insightful conclusions about the tourism in Thessaloniki.
- Get the country given the city
- Get the coordinates
- Create the map

![image](https://user-images.githubusercontent.com/95586847/180658666-73d14e7c-ff09-41d5-8ff9-a389f72c5baa.png)

## 4. Sentiment Analysis 

### 4.1 Polarity Score
### 4.2 Most Common Words in Positive and Negative Reviews 
### 4.3 Polarity Score per Restaurant 

## 5. User Profiling

### 5.1 Gender
### 5.2 Age Group

