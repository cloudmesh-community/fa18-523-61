## Technology Project - Not Ready for Review

## Abstract

This project will provide a thorough analysis, and detailed, informative document pertaining to text mining using the Twitter API and Python. The project objectives consists of applying text mining and Natural Language Processing (NLP) techniques and processes to a dataset that was pulled from the social media site Twitter. 

## Introduction
  
  Twitter allows individuals and organizations to post short messages called tweets. Individuals can follow other sites within Twitter to receive their tweets and to stay informed in subjects that appeal to them. Twitter is also thought of as an instant messaging and micro-blogging application that allows users to communicate their opinions and thoughts in a completely open and uninhibited manner. One major component of Twitter is the hashtag. Users can append a hashtag ‘#’ in front of a word or phrase within their tweet in order to categorize them so other users can find and contribute to your tweet. The hashtag can quickly draw attention to, and promote your tweet very effectively. The implications of how the data on Twitter can be used are simply astounding. In particular, Twitter is used by businesses to find new customers, market new products, find marketplace trends, and many other uses. Data Scientists can mine the data on Twitter and discover new insights and uses of the data through the applications of machine learning algorithms. I will be examining through the use of the Twitter API, how to mine for tweets that contain the hashtags #dog, #cat, or both. We will then clean up the data and apply two different machine learning classification algorithms to ascertain just how effective it is to classify tweets into specific categories. This type of analysis can have far-reaching implications as aforementioned previously, and specifically with this exercise we can try to answer the question if a person is a dog person, a cat person, or both based solely on the information in their tweets. 
** Insert Twitter references **

## Data 

  For this exercise, I created a Twitter API account and used Python to connect to Twitter directly using a set of credentials that were supplied to me. Using a python script, I created two sets of data; one for tweets that contained the hashtag #dog and a second dataset that contained tweets with the hashtag #cat. After the data is pulled, the json data is converted into dataframes using the pandas package. I intend to store the data within a MongoDB database within the AWS platform, for which I’ve created an account.  I would also like to provide appropriate visualizations using the Python Matplotlib library.    
