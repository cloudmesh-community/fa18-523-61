# Twitter Text Mining using Python. MongoDB, and Amazon Web Services  - :hand: fa18-523-61

-- working title, not finalized yet..

| Jay Stockwell
| jaystock@iu.edu
| Indiana University
| hid: fa18-523-61
| github: [:cloud:](https://github.com/cloudmesh-community/fa18-523-61/blob/master/project-report/report.md)

---
Keywords: Twitter, Text Mining, Python, MongoDB, Amazon Web Services
---

## Abstract

This term paper will provide a thorough analysis, and detailed, informative document pertaining how the Twitter API, in conjunction with Python and MongoDB Atlas can provide an effective solution for collecting and analyzing tweets. The paper's objectives are to provide a thorough understanding pertaining to how the twitter API works, how twitter data is constructed, how Python's tweepy library works to collect data, and how MongoDB Atlas cloud service provides a robust environment to store twitter data for future analysis. The paper will also discuss the implications of using the Twitter app and its data within the realm of Big Data and Natural Language Processing. 


## Introduction
  
Twitter allows individuals and organizations to post short messages called tweets. Individuals can follow other sites within Twitter to receive their tweets and to stay informed in subjects that appeal to them. Twitter is also thought of as an instant messaging and micro-blogging application that allows users to communicate their opinions and thoughts in a completely open and uninhibited manner. One major component of Twitter is the hashtag. Users can append a hashtag ‘#’ in front of a word or phrase within their tweet in order to categorize them so other users can find and contribute to your tweet [@www.tech-faq]. The hashtag can quickly draw attention to, and promote your tweet very effectively. The implications of how the data on Twitter can be used are simply astounding. In particular, Twitter is used by businesses to find new customers, market new products, find marketplace trends, and many other uses. Data Scientists can mine the data on Twitter and discover new insights and uses of the data through the applications of machine learning algorithms. I will be examining through the use of the Twitter API, how to mine for tweets that contain the hashtags #dog, #cat, or both. We will then clean up the data and apply two different machine learning classification algorithms to ascertain just how effective it is to classify tweets into specific categories. This type of analysis can have far-reaching implications as aforementioned previously, and specifically with this exercise we can try to answer the question if a person is a dog person, a cat person, or both based solely on the information in their tweets. 

## Implementation

Twitter provides a dedicated API platform for developers to allow for the development of custom applications to collect and use
tweets. This API can be used for both personal and business purposes. Users can tap into the vast social network to for numerous reasons such as collecting specific tweets and placing in a datastore, integrating tweets from twitter within your own website or application, monitor your own twitter accounts to see how individuals are engaging [@www-developer-twitter]. Twitter provides serveral different API's for individuals to use based on their final goals of how they intend to leverage the data. For most basic needs, the standard API will work. However, twitter offers an Enterprise API for organizations that depend on Twitter for their day-today business. 

In order to gain access to Twitter data through the API, users are required to create a Twitter account. The signup process requires users to provide basic user information, as well information about your purpose and intent of your objectives with Twitter. Upon completing the sign up process, Twitter reviews your information and then assigns 4 keys that will be required for authentication between your application and Twitter. These 4 keys consist of consumer tokens and secrets that provide application authentication, and access tokens and secrets that provide the actual user or account authentication [@www-developer-twitter-basics]. 

One method of connecting to, and collecting Tweets is through Python. Python is an open source, general purpose programming language that has gained tremendous traction in the data science field recently due to it's ease of use and the availability of many different toolkits that can be implemented to complete data science related tasks. Python toolkits such as numpy, sklearn, pandas. and matplotlib can be leveraged to apply statistical analysis, machine learning algorithms, and quick visualizations using your data [@www-coursera-python]. 

As Python has gained momentum with the Data Science field, another field in which the language is gaining ground is Big Data. Python is now compatible to work with the popular big data tool Hadoop [@www-whizlabs-com]. 

> "Python consists of Pydoop package which helps in accessing HDFS API and also writing Hadoop MapReduce programming. Besides that         Pydoop enables MapReduce programming to solve complex big data problems with minimal effort [@www-whizlabs-com]".

Python is also very scaleable within this environment. Another great component is that Python has a very large, robust user community that users can reach out to for guidance on all sorts of coding related topics. Due to the popularity of the language, experienced users are extremely willing to participate in the community to facilitate its growth and continued usage with the programming world.  

Python can be leveraged using a basic shell program, which can accomplish basic tasks, or with an interpreter or IDE (Integrated Developer Environments). An IDE is a dedicated program, integrated with several tools such as debuggers, build and execution tools, syntax highlighting, and source control tools, that are specifically used to writing software code [@www-realpython-com]. Some examples pf well known Python specific IDE programs are PyCharm, Spyder, and Thonny. When tasked with developing more sophisticated Python code for data science purposes, it is a good practice to use a dedicated code editor well suited to the task.  

In regards to working with Twitter, there is a library entitled Tweepy that can be installed 

Tweepy currently supports oauth authentication and authentication is handled via the tweepy.AuthHandler class in python [@www-tweepy-io]. Oauth authentication is considered the standard method for token authentication by 3rd-party applications such as Facebook and Twitter. Oauth works on behalf of the end user to provide a token which authorizes specific information to be shared between applications [@www-searchmicroservices]. Some examples pf well known Python specific IDE programs are PyCharm, Spyder, and Thonny. 


The requirements for this project are to run a python script to collect twitter data, specifically tweets with the hashtags #cats and #dogs. Next, is to store the twitter data within a MongoDB database using my local computer and also in the cloud using MongoDB. In order to pull twitter data, users must create a Twitter API account through the Twitter developers website. After creating an account, users wil be provided with four distinct security tokens that users will need in order to connect to the Twitter API through Python. 

Next, I installed the latest version of Python, which is version 3.7.1. Python is an open source general purpose programming language that is very useful for data science projects. There are numerous libraries available to install within Python that will help you accomplish your end goal. For this project, the primary library that I want to use for collecting twitter data is tweepy. Tweepy is designed to handle multiple aspects of twitter tweet collection including authentication, connection, session management, and reading and routing incoming messages [@www-tweepy-io]. 



Once tweepy is set up and the user passes through the authentication step, users can now run begin to collect tweets. Tweepy collects tweets in real-time, so the script will be collecting tweets that were released just prior, or during the implementation of the script.  
The tweepy program in Python can only collect 100 tweets at a time, so the script contains a function to run in a loop to collect a set number of tweets as defined by a 'MaxTweets' parameter. Once that parameter value is met, the function terminates. 

## Design

## Data 

For this term paper, I created a Twitter API account and used Python to connect to Twitter directly using a set of credentials that were supplied to me. Using a python script, I created two sets of data; one for tweets that contained the hashtag #dog and a second dataset that contained tweets with the hashtag #c .at. After the data is pulled, the json data is converted into dataframes using the pandas package. 

Twitter data, when extracted, is in JSON format. JSON (Javascript Object Notation) is a data interchange format that is both easy for humans to read and write, and easy for machines to parse and implement [@www-json-org]. A json object is basically a set of key value pairs ending contained within two braces. 

-- add JSON object image here 

A json array is essentially a collection of key values contained within two brackets

-- add JSON array image here

Twitter JSON data is comprised of many different components, all of which are used to describe individual tweets. 

>> "At Twitter we serve many objects as JSON, including Tweets and Users. These objects all encapsulate core attributes that describe      the object. Each Tweet has an author, a message, a unique ID, a timestamp of when it was posted, and sometimes geo metadata shared by    the user. Each User has a Twitter name, an ID, a number of followers, and most often an account bio [@www-developer-twitter]".

Below is an example of a tweet and a description of the content:

{
  "created_at": "Thu Apr 06 15:24:15 +0000 2017",
  "id_str": "850006245121695744",
  "text": "1\/ Today we\u2019re sharing our vision for the future of the Twitter API platform!\nhttps:\/\/t.co\/XweGngmxlP",
  "user": {
    "id": 2244994945,
    "name": "Twitter Dev",
    "screen_name": "TwitterDev",
    "location": "Internet",
    "url": "https:\/\/dev.twitter.com\/",
    "description": "Your official source for Twitter Platform news, updates & events. Need technical help? Visit https:\/\/twittercommunity.com\/ \u2328\ufe0f #TapIntoTwitter"
  },
  "place": {   
  },
  "entities": {
    "hashtags": [      
    ],
    "urls": [
      {
        "url": "https:\/\/t.co\/XweGngmxlP",
        "unwound": {
          "url": "https:\/\/cards.twitter.com\/cards\/18ce53wgo4h\/3xo1c",
          "title": "Building the Future of the Twitter API Platform"
        }
      }
    ],
    "user_mentions": [     
    ]
  }
}

The tweets follow a parent-child construction. All tweets contain a user object which can also contain a geo-tagged child object describing the geographic location of where the tweet originated. The tweet also contains an entities object that consists of information such as assigned hashtags, URLs, user mentions, and any sort of media material [@www-developer-twitter]. 

I intend to store the data within a MongoDB Atlas Cluster run using the AWS platform, for which I’ve created an account. I would also like to provide appropriate visualizations using the Python Matplotlib library.    

## Results

## Conclusion








