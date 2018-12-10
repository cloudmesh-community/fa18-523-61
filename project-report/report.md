# Twitter Text Mining with Python and MongoDB  - :smiley: fa18-523-61


| Jay Stockwell
| jaystock@iu.edu
| Indiana University
| hid: fa18-523-61
| github: [:cloud:](https://github.com/cloudmesh-community/fa18-523-61/blob/master/project-report/report.md)

---
Keywords: Twitter, Text Mining, Python, MongoDB, Amazon Web Services, Tweepy, Naive Bayes, Neural Networks
---

## Abstract

The paper's objectives are to provide a thorough analysis, and detailed, informative document pertaining how the Twitter API tool, in conjunction with Python and MongoDB Atlas can provide an effective solution for collecting and analyzing tweets. Additionally, other  objectives are to provide a thorough understanding pertaining to how the twitter API works, how twitter data is constructed, how Python's tweepy library works to collect data, and how MongoDB Atlas cloud service provides a robust environment to store twitter data for future analysis. We will also discuss the implications of using the Twitter app and its data within the realm of Big Data and Natural Language Processing. 


## Introduction
  
Twitter allows individuals and organizations to post short messages called tweets. Individuals can follow other sites within Twitter to receive their tweets and to stay informed in subjects that appeal to them. Twitter is also thought of as an instant messaging and micro-blogging application that allows users to communicate their opinions and thoughts in a completely open and uninhibited manner. One major component of Twitter is the hashtag. Users can append a hashtag ‘#’ in front of a word or phrase within their tweet in order to categorize them so other users can find and contribute to your tweet [@www.tech-faq]. The hashtag can quickly draw attention to, and promote your tweet very effectively. The implications of how the data on Twitter can be used are simply astounding. In particular, Twitter is used daily by businesses to find new customers, market new products, find marketplace trends, and many other uses. 

Twitter data, and social media data in general, represent a huge component of Natural Language Processing (NLP). NLP in a nutshell is the ability of machines to decipher and understand human language [@www-searchbusinessanalytics]. This can sometimes pose a challenge because language can tend to have multiple meanings and contexts, and can prove to be very ambiguous to machines which tend to rely on highly structured and precise programming languages [@www-searchbusinessanalytics].  Recent advances in NLP technology have eliminated some of the challenges facing NLP, specifically with part-of-speech tagging and Natural Language Understanding, and have greatly improved how semi-structured and unstructured text data is analyzed and leveraged today. NLP is largely based on the deep learning concept, which is prevalent in the emerging world of Artificial Intelligence. Deep learning algorithms look for patterns in data and use those identified patterns to help machines derive understanding from textual data. Another aspect of NLP that has major implications for Twitter is Sentient Analysis. Sentient Analysis can help organizations ascertain whether a particular product is seen in a positive or negative way based on user comments or reviews. Sentient models can analyze the language components and provide valuable data about products and/or services that can affect corporate decision making and product marking and placement strategies.   

Data Scientists can mine the data on Twitter and discover new insights and uses of the data through the applications of machine learning algorithms, such as the deep learning algorithms mentioned earlier. For example, users can examine through the use of the Twitter API, how to mine for tweets that contain the hashtags #dog, #cat, or both. Users can also examine how to clean up the data in python and  also examine and contrast two different machine learning classification algorithms to ascertain just how effective it is to classify tweets into specific categories. This type of analysis can have far-reaching implications as aforementioned previously, and specifically we can try to answer many questions about an individuals tastes, interests, and hobbies based solely on the information in their tweets. Users can also examine how effective twitter data is being stored within cloud database, in particular MongoDB Atlas to determine if that platform provides an effective storage infrastructure for json-styled, semi-structured data.     

## Twitter API and Python Implementation

Twitter provides a dedicated API platform for developers to allow for the development of custom applications to collect and use
tweets. This API can be used for both personal and business purposes. Users can tap into the vast social network to for numerous reasons such as collecting specific tweets and placing in a datastore, integrating tweets from twitter within your own website or application, monitor your own twitter accounts to see how individuals are engaging [@www-developer-twitter]. Twitter provides serveral different API's for individuals to use based on their final goals of how they intend to leverage the data. For most basic needs, the standard API will work. However, twitter offers an Enterprise API for organizations that depend on Twitter for their day-today business. 

In order to gain access to Twitter data through the API, users are required to create a Twitter account. The signup process requires users to provide basic user information, as well information about your purpose and intent of your objectives with Twitter. Upon completing the sign up process, Twitter reviews your information and then assigns 4 keys that will be required for authentication between your application and Twitter. These 4 keys consist of consumer tokens and secrets that provide application authentication, and access tokens and secrets that provide the actual user or account authentication [@www-developer-twitter-basics]. 

One method of connecting to, and collecting Tweets is through Python. Python is an open source, general purpose programming language that has gained tremendous traction in the data science field recently due to it's ease of use and the availability of many different toolkits that can be implemented to complete data science related tasks. Python toolkits such as numpy, sklearn, pandas. and matplotlib can be leveraged to apply statistical analysis, machine learning algorithms, and quick visualizations using your data [@www-coursera-python]. 

As Python has gained momentum with the Data Science field, another field in which the language is gaining ground is Big Data. Python is now compatible to work with the popular big data tool Hadoop [@www-whizlabs-com]. 

> "Python consists of Pydoop package which helps in accessing HDFS API and also writing Hadoop MapReduce programming. Besides that         Pydoop enables MapReduce programming to solve complex big data problems with minimal effort [@www-whizlabs-com]".

Python is very scaleable within this type of environment. Another great component is that Python has a very large, robust user community that users can reach out to for guidance on all sorts of coding related topics. Due to the popularity of the language, experienced users are extremely willing to participate in the community to facilitate its growth and continued usage within the programming world.  

Python can be leveraged using a basic shell program, which can accomplish basic tasks, or with an interpreter or IDE (Integrated Developer Environments). An IDE is a dedicated program, integrated with several tools such as debuggers, build and execution tools, syntax highlighting, and source control tools, that are specifically used to writing software code [@www-realpython-com]. Some examples of well known Python specific IDE programs are PyCharm, Spyder, and Thonny. When tasked with developing more sophisticated Python code for data science purposes, it is a good practice to use a dedicated code editor well suited to the task.  

In regards to working with Twitter, there is a dedicated library entitled Tweepy which can be loaded into Python and installed along with any other required libraries and toolkits. Users will need to use the pip command at a terminal screen in order to install tweepy. PIP is a package management system used by Python to install and manage larger software packages [@www-en-wikipedia-pip]. 

```
pip install tweepy
```

After installation is complete, users will need to use the import function to fully load the tweepy program into the python script that's currently in development.

```python
import tweepy
```

The next step is authentication between the Twitter API and python. As mentioned earlier, there are 4 required keys needed for this step for which Tweepy is responsible for completing. Tweepy currently supports OAuth authentication and authentication is handled via the tweepy AuthHandler class in python [@www-tweepy-io]. Oauth authentication is considered the standard method for token authentication by 3rd-party applications such as Facebook and Twitter. Oauth works on behalf of the end user to provide a token which authorizes specific information to be shared between applications [@www-searchmicroservices].  There are four variables in the python code that will be used to hold the security information

```python
consumer_key=YOUR_CONSUMER_KEY
consumer_secret=YOUR_CONSUMER_SECRET
access_token_key=YOUR_ACCESS_TOKEN
access_token_secret=YOUR_ACCESS_TOKEN_SECRET
```

Once tweepy is set up and the user passes through the authentication step, users can now begin further development on python code that can be implemented against Twitter data.. Tweepy collects tweets in real-time, so the script will be collecting tweets that were released just prior, or during the implementation of the script. The tweepy program in Python can only collect 100 tweets at a time, so the script can be built to contain a function which runs in an iterative loop to collect a set number of tweets as defined by a 'MaxTweets' parameter. Once that parameter value is met, the function terminates. 

Next, users need to install the latest version of Python, which is version 3.7.1. Python is an open source general purpose programming language that is very useful for data science projects. There are numerous libraries available to install within Python that will help you accomplish your end goal. One of the most popular libraries available for working with twitter data in python is tweepy. Tweepy is designed to handle multiple aspects of twitter tweet collection including authentication, connection, session management, and reading and routing incoming messages [@www-tweepy-io]. 

## Data

Twitter data, when extracted, is in JSON format. JSON (Javascript Object Notation) is a data interchange format that is both easy for humans to read and write, and easy for machines to parse and implement [@www-json-org]. A json object is basically a set of key value pairs ending contained within two braces. This format borrows heavily from the Javascript programming language, hence the Javascript component of the term [@www-packtpub-com-json]. The format is considered to be structured, as you would expect to see relational data within a table, but it's considered to be thought of as semi-structured which  "..the structure is either flexible or not fully predefined. It is sometimes also referred to as a self-describing structure [@www-packtpub-com-json]." The JSON datatype has proven to be very popular and has garnered wide usages with web sites due to the effective way in which JSON data can be exchanged between client and server web applications [@www-packtpub-com-json]. Below is sample JSON object: 

```json
{"first name":"Jay", "last name":"Stockwell", "hometown":"Louisville", "hobby": "playing guitar"} 
```

A json array is essentially a collection of key values contained within two brackets

```json
{
  "first name":"Jay", 
  "last name":"Stockwell", 
  "hometown":"Louisville", 
  "hobby":"playing guitar"
  "favorite cars":["Porsche","Lamborghini","Jeep"]
}
```

Twitter JSON data is comprised of many different components, all of which are used to describe individual tweets. 

> "At Twitter we serve many objects as JSON, including Tweets and Users. These objects all encapsulate core attributes that describe       the object. Each Tweet has an author, a message, a unique ID, a timestamp of when it was posted, and sometimes geo metadata shared by   the user. Each User has a Twitter name, an ID, a number of followers, and most often an account bio [@www-developer-twitter]".

The tweets follow a parent-child construction. All tweets contain a user object which can also contain a geo-tagged child object describing the geographic location of where the tweet originated. The tweet also contains an entities object that consists of information such as assigned hashtags, URLs, user mentions, and any sort of media material [@www-developer-twitter]. The data record also contains a flag to indicate if the tweet has been retweeted, or has been forwarded by someone else to another person. A retweet is typically comprised of someone else's comments that a user would like to share.  

## Twitter Cloud Storage

There are many options available today to store twitter data within a cloud storage platform. Cloud storage consists of storing data within logical pools that can span multiple servers and multiple locations throughout many locations [@www-en-wikipedia-cloud]. Cloud services can be accessed through a dedicated cloud service platform, and website APIs such as cloud desktop storage and gateways. [@www-en-wikipedia-cloud].  Some of the main players in today's cloud computing market are Amazon Web Services, Microsoft Azure, and Google iCloud. 

Amazon Web Services (AWS) provides a portfolio of services that can help organizations deal with the voluminous amounts of data that's available in Twitter. AWS provides a cloud storage service called S3 which is capable of storing data of any type from a variety of sources including web sites, mobile apps, and even IoT sensors [@www-aws-amazon-s3]. Used in conjunction with Amazon Glacier, and Amazon Glue, one could build a secure data lake in the cloud that could be set up to contain streaming twitter data. Once the data is in the data lake, one can take advantage of cutting-edge advanced machine learning and analytics capabilities available through additional Amazon services such as AWS Athena (Interactive analytics), AWS Kinesis (Real-Time Analytics), and AWS Sagemaker and Deep Learning AMIs
[@www-aws-amazon-s3].


![AWS S3 Data Lake [@www-aws-amazon-s3]](images/fa18_523_61_AWS_DataLake.png){#fig:AWSS3DataLake}


A lot of organizations today leverage the power and scalability of the S3 platform and come to rely on the system for its day-to-day data needs. That reliability was tested during an AWS S3 outage that occurred on February 27th, 2017 that effected Amazon's entire US-EAST-1 region. This outage caused widespread website outages and vast disruptions to Amazon's clients. The issue was caused by an Amazon employee typing an incorrect command which caused several key subsystems to go offline [@www-theverge-s3]. This was an embarassing incident for Amazon that just goes to show how important cloud services have become in recent years, and how much some clients depend on these services.  

In addition to the S3 platform, Amazon includes other services that allow users to set up and manage virtual machines and virtual cloud platforms. Users can create a cloud cluster leveraging one of these services and run a different database application that is more suitable to their data needs. MongoDB Atlas, an open source database storage system that provides support for JSON document style data, is one of those types of applications that can be stood up and managed on an Amazon Virtual Private Cloud (VPC). Mongo Atlas provides a platform from which users can create and manage their own clusters, as well as set up automation jobs to manage provisioning and deployment tasks [@www-mongodb-com-atlas]. Users are required to create an account with Mongo DB Atlas, which provides a minimum of 512 MB of storage for a free cloud database, but can be updated to 10 GB or more along with dedicated RAM, backups, and performance optimization with the creation of a dedicated cluster [@www-mongodb-com-atlas]. In addition to running on Amazon VPC, MongoDB Atlas can also run on Microsoft Azure and Google Cloud. 

Connecting to MongoDB Atlas from python is fairly straightforward and requires the pymongo python library to be installed. The pymongo library contains several tools that enables users to connect to their MongoDB data, either on their local machine, or a database hosted on a MongoDB Atlas cluster. Users must use the pip method from a command prompt or terminal screen and run the following command:

```
python -m pip install pymongo
```

After the pip command is completed and pymongo is installed, the library must be imported into python using the following simple command:

```python
import pymongo
```

The Mongo Client component is one of the pymongo tools allowing for python to connect to a MongoDB database. Connecting to a local instance of MongoDB is simple and requires that the software is fully installed and the MongoDB service is up and running.Also, port 27017 must be available on your machine in order for the two applications to communicate properly. The python command for connecting to a local MongoDB instance is as follows:

```python
client = pymongo.MongoClient("localhost",27017)
```

Connecting to a MongoDB Atlas cluster involves a few more steps. First, before you can start up a cluster, there are a few requirements that need to be met. Users must have the correct TLS/SSL support in place and be able to have the correct SNI driver installed in order to connect [@www-docs-mongodb-atlas]. Users must also add their IP address to the MongoDB Atlas Whitelist. This ensures that the only connections allowed will be listed in MongoDB's whitelist [@www-docs-mongodb-atlas]. Next, users must create a user account with Admin access in order to be able to administer the cluster. After those steps are complete, and the cluster has been started up, users must choose a connection method to use in order to connect to another application. The connection dialog contains different connection strings for different versions of applications including Java, C, C++, Perl, Ruby, and Python. To set up a connection between MongoDB Atlas and Python, users will need to select a URI connection string based on their version of Python. Next, they will need to paste that string within their python script within the following pymongo command:

```python
client = pymongo.MongoDB(mongodb://USERNAME:PASSWORD@cluster0-sample-mongodb.net:27017/<DATABASE>
```

After this is complete, and you're able to connect without any issues, you can begin to create databases, collect and insert data into the MongoDB database, as well as other data related tasks. Just a note on connecting to MongoDB, users will sometimes receive error messages pertaining to DNS connection errors. To resolve this, users need to install the dnspython library using the pip method and importing the resolver tool from the dnspython library within python. 

```python
python -m pip install dnspython
```
```python
from dnspython import resolver
```

Once fully connected to MongoDB, you begin to 'listen' or search for tweets that contain a specific word, phrase, user, #hashtag, or any other piece of information that you're interested in mining for. There's a couple of ways to set up the search criteria, but typically a variable is created that contains the search words such as listed below:

```python
count = 50
q="cats"
search_results=api.search.tweets(count=count,q=q)
```

You can configure tweepy to work in a search or streaming manner. Tweepy has a class entitled StreamListener that will access the Twitter API and pull all tweets are created using the specified criteria [@www-pythondata-twitter]. Once executed, the script will continue streaming until the script is stopped. The api.search method will provide a collection of tweets based upon a count variable specified earlier. One thing of note is the Tweepy will only return 100 tweets at a time, so the script will need to contain an iterative loop function to run continuously until the value specified in the count variable is met. 

After the script is run, the data can now be inserted into the MongoDB Atlas database. The pymongo library includes an insert function that will allow the user to insert either one record, or many records into the database. In order to use the insert many function, you will need to create a collection database object. A MongoDB collection is essentially a collection of documents, or in relation to Twitter data, a collection of json documents [@www-docs-mongodb-collections]. A collection can be thought of as being similar to a SQL relational table [@www-blog-jlevente-intro]. The collection, if it doesn't already exist, can be created within the insert statement itself. Below are two examples:

```python
# Insert one record only
db = mydb.insert_one(mydict)

# Insert multiple records
db = mydb.insert_many(mydict)
```

The python script can be run multiple time to continously gather tweets. However, it is important that we don't collect the same tweets every time we run the script. Therefore, it is adviseable to create an index object after the initial connection to the MongoDb database and database table. This will ensure that each object is properly indexed and contains a unique ID field. Once the script is run subsequent times, an argument can be put in place to check the ID field and ensure that duplicate tweets are not being added. 

Twitter Data contained within the MongoDB database can be queried from within Python using specific command line arguments and functions from the pymongo library. The argument findone() will return the very first record in the database and will include every item associated with that record. With Twitter data, the findone() argument will return all of the components of the first tweet collected such as key, timestamp, description, user, etc. If you want to zero in on one specific item within the tweet, you can add some additional information to the findone() argument. For example,if a user wanted to see the key of the first tweet, they would add 'key' to the findone() argument as findone.key(). The argument needs to also contain the data collection that we are querying. 

To return all of the records in the database, a cursor object must be created in the python script that will allow the user to read and analyze all of the records within the collection [@www-blog-jlevente]. A cursor can be created by setting up a find() argument within a collection. You can also limit the results by including a limit argument set to the desired number of records. 

MongoDB Atlas was designed to handle large datasets by spreading the data among many servers with the cloud computing platform [@www-mongodb-bigdata]. MongoDB can also be connected to a Hadoop instance to deal with the upcoming challenges that are presented by Big Data. This creates an ideal environment to house streaming Twitter data as MongoDB is perfect for document data types such as JSON. MongoDB is also thought of as being a great platform for working with Big Data because of the high scalability offered by MongoDB [@www-blog-jlevente-intro]. However, there have been some points of contention that have arisen with NoSQL databases such as MongoDB. Some users that have used MongoDb to store twitter data have reported issues related to duplicate data, which was addressed earlier with the creation of an index. Another issue is that because of the structure of Twitter data and the document storage type, it is very hard, if not impossible to do SQL style joins within the data [@www-sarahmei-com]. Social media data is highly unstructured, and individuals that are accustomed to working with relational SQL based databases may find this type of document styled data very hard to understand, analyze, and construct effective queries against. 

Conversely, querying and analyzing twitter data in python is a compelling and direct way to open many new doors to insights. 


## Data Science Algorithms for Twitter Data

There are numerous algorithms available to use in Python when running a script against a Twitter dataset. It's a good idea to perform some dedicated research and make a determination on which algorithms will accomplish your objectives. Deep Learning algorithms such as Neural Networks are very effective when implemented against twitter data, and can be compared using accuracy scores and performance metrics to other similar algorithms such as the Naive Bayes classification model. 

The Naïve Bayes classification method is based on Bayes Theorem probability theory to classify data into distinct classes.  The method assumes independence between all of the attributes used in the algorithm and it works on the assumption that a particular feature in a class in unrelated to the rest of the features included in the analysis [@www-analyticsvidhaya-nb]. Naive Bayes is a fairly simple algoritm to set up, and it runs very effectively against very large datasets such as those used in Big Data. 

Below is the mathematical formula that comprises the algorithm. The formula follows the Bayes Rule of Probability:

![Bayes Rule of Probability [@www-analyticsvidhaya-nb]](images/fa18_523_61_Bayes_Rule.png){#fig:BayesRuleofProbability}

The foundation of the formula is that it calculates the posterior probability P(c|x) from the other variables in the equation, P(c), P(x), and P(x|c) [@www-analyticsvidhaya-nb].

The Naive Bayes classification method has gained popularity recently with usage as an effective spam filter, text analysis, and medical diagnosis tool. Users are able to utilize the multinomial Naïve Bayes model as it appears to be more suitable for text classification by explicitly modeling the word counts and makes adjustments to any underlying calculations involved. 

Another popular algorithm to use with Twitter data is neural networks. Neural networks function as an information processing model that closely mirrors how biological nervous systems , specifically neurons, process information [@www-doc-ic-ac-uk]. Neural networks make predictions by learning the relationships between your data features and other previous observations. This approach works by feeding data into an input layer that goes through a series of transformations within hidden layers until a final transformation occurs and a final output is produced. Deep neural networks go a step further due to the larger number of nodes or layers that the data passes through in a complex, multi-step process of pattern and correlation recognition [@www-skymind.ai].  Working with more layers provides more opportunities for the data to train on the features abd patterns recognized in the previous layer, which in turn produces a more and more complex hierarchy know as a feature hierarchy [@www-skymind.ai]. 

Neural networks are popular in natural language classification tasks because of the ability for neural networks to create an embedded layer. Through vectorization, the words in the embedded layer become mathematical arrays. These vectors can be very useful in text classification. Deep neural networks have gained traction with sentiment analysis in recent years due to the increased user requirements for this type of analysis, and how this analysis can handle increasing levels of complexity with very large unstructured data sets, some of which is not readily apparent [@www-researchgate.net]. 

## Running a Twitter Script in Python

There are multiple ways that users can set up python and perform some basic text mining against Twitter. The scenario below is to design a script that pulls tweets with the hashtags #cats and #dogs. Working with these hashtags, Using python, users can generate a simple script that can be used to classify if a person is a cat or dog person based on their tweets. Users evaluate the performance and accuracy of the two classification algorithms used, as well as evaluate any issues and challenges that arose during their analysis.  

### Python Libraries

Below is a sample list of python libraries that can be used for twitter analysis:

```python
    import tweepy
    import matplotlib.pyplot as plt
    import matplotlib
    !pip install tweepy
    import sys
    import jsonpickle
    !pip install jsonpickle
    import os,json
    import pandas as pd
    import numpy
    import re
    from wordcloud import WordCloud, STOPWORDS
    import warnings
    import sklearn
    import sklearn.metrics 
    from sklearn import metrics
    import sklearn.naive_bayes
    from sklearn.naive_bayes import MultinomialNB
    from sklearn.metrics import classification_report
    from sklearn.metrics import confusion_matrix
    import sklearn.svm
    import sklearn.neighbors
    import sklearn.neural_network
    from sklearn.feature_extraction.text import CountVectorizer
    import seaborn as sns
```

From the sklearn library, users can create a function to gauge the precision scores from the two algorithms that will be used later in the script. The precision scores will help assess whether a record was classified incorrectly, for example a record that is labeled a positive when it should have been labeled negative [@www-scikit-learn-ps].

```python
    def print_score(Ytrue,Ypred):
      s = (sklearn.metrics.precision_score(Ytrue,Ypred),
              sklearn.metrics.recall_score(Ytrue,Ypred),
              sklearn.metrics.f1_score(Ytrue,Ypred))
      print('Precision: {:0.3}\nRecall: {:0.3}\nF-Score: {:0.3}\n'.format(*s))
```      
The next step in the code is authentication with the Twitter API. The concepts behind the authentication process were discussed earlier in the paper. If Twitter is unable to authenticate your account with the provided credentials, a "Can't Authenticate" message is display and the script terminates.   

```python
    """twitter credentials. Removed for security reasons."""
    Credentials file format:
    consumer_key=YOUR_CONSUMER_KEY
    consumer_secret=YOUR_CONSUMER_SECRET
    access_token_key=YOUR_ACCESS_TOKEN
    access_token_secret=YOUR_ACCESS_TOKEN_SECRET

    """Replace the API_KEY and API_SECRET with your application's key and secret."""
    auth = tweepy.AppAuthHandler(consumer_key, consumer_secret)

    api = tweepy.API(auth, wait_on_rate_limit=True,
				       wait_on_rate_limit_notify=True)

    if (not api):
        print ("Can't Authenticate")
        sys.exit(-1)
```        
Now that the user is authenticated, they can specify the search criteria for the specific tweets needed for identification and collection. A variable called 'SearchQuery' contains the #cats hashtag that users may want to search on, the maxTweets variable contains the maximum number of tweets to be collected, the 'tweetsperQry' is set to 100 as this is the maximum amount of tweets the Tweepy API is allow to gather during one iteration using the search function of the API. The 'fname' contains the name of the file in which the tweets will be collected.     

```python
"""Information about the type of tweets we want to find as well as how many"""
searchQuery = '#cat'  # this is what we're searching for
maxTweets = 2000 # Some arbitrary large number
tweetsPerQry = 100  # this is the max the API permits
fName = 'cat_tweets.txt' # We'll store the tweets in a text file.
```

Since the Tweepy API only allows 100 tweets per iteration, the script contains a functions that runs in a loop until the maxTweets value has been reached. If any issues arise, the function will terminate.

```python
    SinceID = None
    max_id = 1
    tweetCount = 0
    print("Downloading max {0} tweets".format(maxTweets))
    with open(fName, 'w') as f:
        while tweetCount < maxTweets:
            try:
                if (max_id <= 0):
                    if (not sinceId):
                        new_tweets = api.search(q=searchQuery, count=tweetsPerQry)
                    else:
                        new_tweets = api.search(q=searchQuery, count=tweetsPerQry,
                                                since_id=sinceId)
                else:
                    if (not sinceId):
                        new_tweets = api.search(q=searchQuery, count=tweetsPerQry,
                                                max_id=str(max_id - 1))
                    else:
                        new_tweets = api.search(q=searchQuery, count=tweetsPerQry,
                                                max_id=str(max_id - 1),
                                                since_id=sinceId)
                if not new_tweets:
                    print("No more tweets found")
                    break
                for tweet in new_tweets:
                    f.write(jsonpickle.encode(tweet._json, unpicklable=False) +
                            '\n')
                tweetCount += len(new_tweets)
                print("Downloaded {0} tweets".format(tweetCount))
                max_id = new_tweets[-1].id
            except tweepy.TweepError as e:
                # Just exit if any error
                print("some error : " + str(e))
                break

    print ("Downloaded {0} tweets, Saved to {1}".format(tweetCount, fName))
```

The iteration loop has completed, and two sample two datasets were created that contains data for the hashtags of #cats and #dogs. Working with twitter data that was contained in dataframes was easier to analyze. The pandas dataframe function was used to take the twitter data from the iteration script and load into two separate dataframes.

```python
dogs = pd.read_json("C:/Users/sample/dog_tweets.txt",lines=True)
cats = pd.read_json("C:/Users/sample/cat_tweets.txt",lines=True)
```
A crucial step when working on a new set of data is to perform some type of data preprocessing and exploration.  This gives you a good sense of that data contents, and if you need to perform some cleansing of the data such as removing null values and incorrect characters or words. 

The first two lines provide a record count. Next, using the dogs dataset, a new column was created entitled tweety and extracted all the URLs and usernames from the collected tweets into that new column. All of the URLS, RT's (retweets), and usernames or twitter handles 
were removed. 

```python
dogs['tweety'] = '' 

#add tweety first part
for i in range(len(dogs['text'])):
    try:
        dogs['tweety'][i] = dogs['text'].str.split(' ')[i][0]
    except AttributeError:    
        dogs['tweety'][i] = 'other'

#Preprocessing tweety. select tweety contains 'RT @'
for i in range(len(dogs['text'])):
    if dogs['tweety'].str.contains('@')[i]  == False:
        dogs['tweety'][i] = 'other'
        
# remove URLs, RTs, and twitter handles
for i in range(len(dogs['text'])):
    dogs['text'][i] = " ".join([word for word in dogs['text'][i].split()
                                if 'http' not in word and '@' not in word and '<' not in word])
dogs['followers_count'][1]
```

Within Natural Language Processing, there are textual components that do not provide any significance to the analysis. These are referred to as stopwords. Some examples of stopwords are *is*, *the*, and *and*. Stopwords should be removed during the processing step to eliminate unnecessary information from being included in the analysis [@www-xpo6-com].  The nltk python library has contains a corpus library of which contains a comprehensive list of stopwords that can be used within the script. 

```python
import nltk
import nltk.corpus
nltk.download('stopwords')
stopwds = list(nltk.corpus.stopwords.words('english'))
## stopwds
```

### Visualizations

Visualizing twitter data in python can be accomplished with the use of a variety of different python packages and tools. One of the more popular and useful libraries for creating plots, charts, and other visualizations is Matplotlib. The Matplotlib python library is a 2D graphical tool that creates publication-like visualizations within a variety of platforms including python, ipython, Jupyter notebooks, and other web applications [@www-matplotlib-org]. "Matplotlib makes easy things easy and hard things possible" [@www-matplotlib-org]. 
Matplotlib installation is straightforward and can be completed with the following code:

```python
import matplotlib
import matplotlib.pyplot as plt
```

Matplotlib contains a tool called pyplot which allows for very simple plotting as well as creating bar charts, line charts, and histograms. The pyplot tool can be utilized to create line and bar charts to show the distribution of twitter users by source. Below is a bar graph depicting the number of followers by source for the #dogs twitter dataset:

![Twitter Source Bar Chart](images/fa18_523_61_twitter_followers.png){#fig:TwitterSourceBarChart}

From looking at the bar chart, one could surmise that the top source for all of the tweets is the iPhone, followed by Twitter for Android, and then the Twitter Web Client application.  This is no surprise given the ubiquitous nature of smart phones today.

The python code used to generate the bar chart is below:

```python
dogs['source_new'] = ''

for i in range(len(dogs['source'])):
    m = re.search('>(.*?)</a', dogs['source'][i])
    try:
        dogs['source_new'][i]=m.group(0)
    except AttributeError:
        dogs['source_new'][i]=dogs['source'][i]
        
dogs['source_new'] = dogs['source_new'].str.replace('', ' ', case=False)

dogs['source_new'].head()

tweets_by_type = dogs.groupby(['source_new'])['favorite_count'].sum()
plt.title('Number of followers by Source', bbox={'facecolor':'0.8', 'pad':0})
tweets_by_type.transpose().plot(kind='bar',figsize=(20, 10))
```

Another effective visualization for analyzing and visualization twitter datasets are wordclouds. Wordclouds depict groupings of words in different sizes depending on how frequently they are displayed within tweets. The Wordcloud python library can be installed using the pip method and imported into the python script with the following commands:

```
python -m pip install wordcloud
```
```python
from wordcloud import WordCloud, STOPWORDS
```

Below is the python code to generate two different wordcloud visualizations; one depicting text and another depicting language.

```python
""" Dogs Text Wordcloud"""
def wordcloud(tweets,col):
    stopwords = set(stopwds)
    wordcloud = WordCloud(background_color="white",stopwords=stopwords,random_state = 2016).
                generate(" ".join([i for i in dogs[col]]))
    plt.figure( figsize=(20,10), facecolor='k')
    plt.imshow(wordcloud)
    plt.axis("off")
    plt.title("Dog DataSet")
wordcloud(dogs,'text')

""" Dogs Language Wordcloud"""
def wordcloud(tweets,col):
    stopwords = set(stopwds)
    wordcloud = WordCloud(background_color="white",stopwords=stopwords,random_state = 2016).
                generate(" ".join([i for i in dogs[col]]))
    plt.figure( figsize=(20,10), facecolor='k')
    plt.imshow(wordcloud)
    plt.axis("off")
    plt.title("Dog DataSet")
wordcloud(dogs,'lang')
```

Below are two wordcloud charts; one illustrating the top words or phrases seen within the Twitter #dogs dataset, and another illustrating the top languages used within the same dataset.

![Text Wordcloud](images/fa18_523_61_wordcloud_text.png){#fig:TextWordcloudPlot}


![Language Wordcloud](images/fa18_523_61_wordcloud_lang.png){#fig:LanguageWordcloudPlot}

The word *dog* is displayed prominently as expected, and there are also some other interesting words such as *love*, *pet*, *first* displayed as well.  There are some other words that were not expected such as *millionaire*, *crypto*, and *trading binance*. This could lead to further research as to how these terms are related to tweets containing the #dog hashtag. The Language wordcloud illustrates that the majority of the tweets are in the English and Japanese language. 

### Machine Learning Algorithms

The Naive Bayes and Neural Networks algorithms can be set up and executed very seamlessly in Python using a variety of libraries. Users can import and implement the Naive Bayes and Neural Network algorithms from the sklearn library. Sklearn contains numerous machine learning algorithmic functions and toolkits, and is a manageable task as far as setup and implementation is concerned. After creating the train and test datasets in python with the desired twitter data, setting up and running the algorithm in Python is straightforward. 

In order to effectively run the algorithms, there are a few model preparation steps needed to be completed. For the cat and dog datasets, the hashtags should be removed and replaced with a filler, non-significant value. 

```python
cats_txt = [x.replace('#cat',"BLAH") for x in cats['text']]
dogs_txt = [x.replace('#dog',"BLAH") for x in dogs['text']]
```

In addition to setting up the algorithm, it is advisable to add in a vectorization component from the sklearn library to incorporate within the algorithm. The vectorization process is used to transform textual information into numerical information that machine learning algorithms such as Naive Bayes and Neural Network can understand and process more efficiently [@www-scikit-learn-feature]. the stopwords component can also be pulled into play at this step to ensure these elements are excluded from this step. Below is the python code to accomplish this:

```python
vectorizer = sklearn.feature_extraction.text.CountVectorizer(cats_txt+dogs_txt, analyzer='word', 
             stop_words=stopwds, min_df=5)
vectorizer.fit(cats_txt+dogs_txt)
cat_tdm = vectorizer.transform(cats_txt).toarray()
dog_tdm = vectorizer.transform(dogs_txt).toarray()
vectorizer.get_feature_names()
```

The next step would entail combining the arrays into one matrix, and then assigning adding in values the class labels.

```python
catdog_tdm = numpy.concatenate((cat_tdm,dog_tdm),axis=0)
Ycat = numpy.array([0 for i in range(len(cats_txt))])
Ydog = numpy.array([1 for i in range(len(dogs_txt))])
Y = numpy.concatenate((Ycat,Ydog),axis=0)
```
At this point, the data must e split into two distinct data sets; one for training and another to test the algoritm. The training dataset is used by the machine learning algorithm to learn about the the data and its possible outcomes. The test data is used to test the algorithm after it has run through the training phase. Typically the training data set is larger in size.  Below is the python code for splitting data into train and test datasets:

```python
Xtrain,Xtest,Ytrain,Ytest = sklearn.model_selection.train_test_split(catdog_tdm, Y, test_size=0.2)
```
In this case, the test data comprised 20% of the dataset while the train data is 80%. 

As mentioned earlier, the Naive Bayes Multinomial algorithm was determined to be one of the more effective algorithms for tweet classification. The python code is below. 

```python
mnb = sklearn.naive_bayes.MultinomialNB()
mnb.fit(Xtrain,Ytrain)
Ypred = nb.predict(Xtest)

print("\nNaive Bayes Performance")
print_score(Ytest,Ypred)
metrics.accuracy_score(Ytest, Ypred)
metrics.confusion_matrix(Ytest,Ypred)
print(Ytest.value_counts())
```

The mnb.fit portion of the code above is fitting the data into the Naive Bayes Algorithm, and the nb.predict function is running the algorithm against the test data. There are some accuracy scores generated as well as a confusion matrix to help gauge whether or not the model was fitted properly. 

The Neural Networks algorithm is another algorithm that has been linked to high performance and results when used with Twitter data. The python code is also straightforward in setting up and requires network hidden layers to be defined as well as the iterations. The python code is below:

```python
nn = sklearn.neural_network.MLPClassifier(hidden_layer_sizes=(30,30,30),max_iter = 500)
nn.fit(Xtrain,Ytrain)
Ypred = nn.predict(Xtest)

print("\nNeural Network Performance")
print_score(Ytest,Ypred)
metrics.accuracy_score(Ytest, Ypred)
cm = confusion_matrix(Ytest, Ypred)
```

## Conclusion

In conclusion, using python to extract and analyze twitter data appears to be an effective tool that can accomplish an emormous amount of tasks. Python's powerful collection of libraries and tools really make a difference in regards to how users can gather results to accomplish their objectives. Python appears to be extremely flexible in allowing many different variables and options to be set. Regarding twitter data, Tweepy appears to be a very fluid and straightfoward tool to setup and program. Creating a twitter api account and setting up the authentication in Python is also very uncomplicated. One caveat in terms of searching for actual tweets is that the number of tweets returned when using the tweepy package is set to 100. Users that want to return more than 100 tweets in their results may need to add in some additional programming to create a iterative loop function in order to get the desired number of tweets. This can add a level of complexity to the script. 

Storing twitter data in the MongoDB Atlas cloud storage system can be an effective solution. Setting up a MongoDB Atlas account is effortless as well as starting up and managing a new cluster. The free tier is offered at no cost and includes up to 512 MB, however, this may inefficient for some, if not most, users who are working with very large amounts of twitter data. In order to perform an effective analysis, large amounts of data is required, and the free tier will probably not meet those requirements.  MongoDB Atlas does offer services at higher pricing tiers that include both scalable RAM and scalable storage. These options may prove to be attractive for enterprise level entities.  MongoDb Atlas has shown some issues at the data level pertaining to duplicate records being captured, however, those issues can be alleviated within Python by including some code that ensures that the ID fields of the tweets are unique. 


## Future Research

Collecting social media for sentiment analysis is another area of interesting research that has arisen. Sentiment analyze can provide data on a more subjective level, as opposed to objective such as what is provided here.  Many new questions arose such as how can using NLP to determine the state or emotion that a certain tweet is conveying, can this be accomplished in python somewhat efficiently, and what are the specific uses for this data. 

## Acknowledgements

The author gratefully acknowledges the input and guidance of Dr. Gregor von Laszewski, specifically in regards to paper syntax rules, bibtex reference usage, and the use of images within the markdown document.






