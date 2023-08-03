<H1 align="center">
Algonquin college
</H1>
<H2 align="center">
CST2208_010 Data Science Topics for BISI Students <BR>
Sentimental Analysis Using NLP <BR>
Professor: Swapnil Kangralkar <BR>
</H2>
<H3 Align="center">
By:<BR>
Harsh Mistry<BR>
HetKumar Patel<BR>
Vidhi Tripathi <BR>
Dhruv Gadhiya<BR>

<p align="center">
  <img src="Image.jpg" alt="Image" width=""/>
</p>


## Overview::memo:
This NLP project is based on the finding the sentimental score for two courier services Canada Post and Purolator according to the customer reviews using python.

## Data Understanding::ledger:
* We collected our data from Canada Post and Purolator by using web scrapping technique from
online reviews. We collected data from November 2021 to current July 2023 so, two years of
data.
>By using beautiful soup library, we fetch our data from the Trustpilot website from HTML format. <BR>
* The dimension of the data is 3 column and 4800 rows for Canada post reviews and nearly equal
for Purolator 3 column and 4791 rows. Where, Columns are Unnamed having row numbers,
customer name who put the review for the service and review column with date.
* Reviews are consisting with emojis which we must remove form the file. Review column of
Canada post having 473242 words whereas, Purolator have 585177.

## Data Cleaning and preparation::label:
Here, we applied four techniques to clean our data.

1. Tokenization: After collecting the data, we applied Tokenization technique into words to break
the input sequence into smaller parts or tokens, such as words, phrases, or sentences. This step
helps in preparing the text data for further analysis and modeling to find the useful information.
SENTIMENTAL ANALYSIS USING NLP 6
2. Lemmatization: It is the process of reducing words to their base from using a morphological
analysis of the words. We tried to apply stemming techniques but after applied we realizes that the
lemmatization is more accurate than it as it represents the original word. Further we applied
lemmatization by using WordNet database to convert the different version of words with the use of
vocabulary analysis to make Lemma (Actual dictionary words).
3. Remove Punctuation: Then we removed some punctuation with string. punctuation from the data
which is unnecessary.
4. Remove Stop Words: We removed stop words from nltk library were, stopwords. words function
to get the list of stop words in English language and stores the list in stop_words. After this step
we removed around 128,280 from the review column of the Canada post file and 165,294 words
from Purolator review column.
5. Remove Emojis: Here, we use regex pattern to match the emojis where ‘\p{SO}’ is Unicode
category which represent the other symbols including emojis helps to match from the review
column.

## Feature Engineering::bangbang:
* We applied TF-IDF (Term frequency- Inverse Document Frequency) vectorization which convert the text data into numerical vectors (Sparse) helps to capture the important words in the document or clustering to retrieve the information.
* TF-IDF downweighs frequently used words that appear in text like “the,” “and” “is” etc., have high term frequencies in most documents but may not have some specific information. So, this method helps to reduce it and helps to focus on more important terms for the analysis.
* Here we apply this technique to convert the text in numerical vectors to find the clusters.

## Applied Models::page_facing_up:
### 1. TextBlob:
* We applied this library on trained ML model that can classify text into various sentiment such as positive, negative, or neutral based on the phrases and words in the review.
* In this model polarity and subjectivity score of the text create sentiment and objectivity. Were,
* Polarity: It the indication of positive, negative, or neutral sentiment of the text. The range of polarity is -1 to +1 where, neutral=0.
* Textblob use the pre-built sentiment lexicon that contains words with their pre- assigned polarity score. For each word library look up for its polarity score in the lexicon and aggregates for that word to calculate overall polarity score.
SENTIMENTAL ANALYSIS USING NLP 7
* Subjectivity: It represent the level of subjectivity in the text. It ranges from 0 to 1. Where, 0= complete objective and 1=complete subjective

### 2. NLTK: (Natural Language Toolkit)
* It consists with comprehensive toolkit provide more control and flexibility for NLP. It is work well on informal languages, slang and emotions which commonly used in social media or on website.
* Here, NLTK works good as compared to textblob.

## Results and Outcome::dart:
* Sentimental score for two different services Canada post and Purolator based on Cost related reviews how customer is satisfied with their fees for posting process. Also, the delivery time service paly crucial role in any mailing services so, here the outcome is based on that and with their customer service experience in terms of sentiment score.
* Here, our team applied two different model Textblob and NLTK based on that the outcome as below for Positive, negative, and neutral sentiment score of the reviews.

| Area  | Canada Post sentiment score | Purolator’s sentimental score |
| ------------- | ------------- | ------------- |
| Cost related reviews  | 0.075  | 0.052 |
| Delivery Time reviews  | 0.604  | 0.740 |
| Customer Service reviews | -0.01 | -0.01 |

| TextBlob Model  | Canada Post sentiment score | Purolator’s sentimental score |
| ------------- | ------------- | ------------- |
| Positive  | 0.67  | 0.22 |
| Negative  | -0.25  | -0.22 |
| Neutral | 2.42 | 0.01 | 

| NLTK Model | Canada Post sentiment score | Purolator’s sentimental score |
| ------------- | ------------- | ------------- |
| Positive  | 0.11  | 0.10 |
| Negative  | -0.50  | -0.11 |
| Neutral | -0.1 | -0.01 |

## Key Findings::old_key:
* Based on average sentiment score of all reviews the TextBlob model represent subjectivity and polarity 0.7 which is good as compared to Purolator (0.52).
*	Total positive review score is 0.67 which is higher than Purolator so, it represents that Canada post have complimentary reviews than Purolator.
*	Both services have nearly equal amount of negative sentiment score, whereas, talking about neutral, Canda post having more neutral than the Purolator’s review.
*	Additionally, NLTK represent the sentiment score for Canada Post -0.01 ≈ -0.009 (Purolator) which represent the Canada post having nearly equal negative review as Purolator.
*	For Cost related review Canada post reviews having high score (0.075>0.0521) showing for cost related Canada post is good than Purolator.
*	About delivery time reviews Canada Post score 0.6<0.74 so, for delivery time their customer is less satisfied as compared to Purolator.
*	Canada post’s customer service is better than Purolator as it is sentiment score is positive 0.011 than Purolator in negative (-0.009)

## Visualization::old_key:
* Let's analyse sentimental score distribution for Canada Post and Purolator.

### Canada Post 
<p align="center">
  <img src="chart 1.jpg" alt="Image" width=""/>
</p>

### Purolator
<p align="center">
  <img src="chart 2.jpg" alt="Image" width=""/>
</p>
