# Twitter Text Mining using Python. MongoDB, and Amazon Web Services  - :hand: fa18-523-61

:o: finalize title

:o: refs missing

-- Still a draft. Images and references will be inserted soon

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

## Twitter API and Python Implementation

Twitter provides a dedicated API platform for developers to allow for the development of custom applications to collect and use
tweets. This API can be used for both personal and business purposes. Users can tap into the vast social network to for numerous reasons such as collecting specific tweets and placing in a datastore, integrating tweets from twitter within your own website or application, monitor your own twitter accounts to see how individuals are engaging [@www-developer-twitter]. Twitter provides serveral different API's for individuals to use based on their final goals of how they intend to leverage the data. For most basic needs, the standard API will work. However, twitter offers an Enterprise API for organizations that depend on Twitter for their day-today business. 

In order to gain access to Twitter data through the API, users are required to create a Twitter account. The signup process requires users to provide basic user information, as well information about your purpose and intent of your objectives with Twitter. Upon completing the sign up process, Twitter reviews your information and then assigns 4 keys that will be required for authentication between your application and Twitter. These 4 keys consist of consumer tokens and secrets that provide application authentication, and access tokens and secrets that provide the actual user or account authentication [@www-developer-twitter-basics]. 

One method of connecting to, and collecting Tweets is through Python. Python is an open source, general purpose programming language that has gained tremendous traction in the data science field recently due to it's ease of use and the availability of many different toolkits that can be implemented to complete data science related tasks. Python toolkits such as numpy, sklearn, pandas. and matplotlib can be leveraged to apply statistical analysis, machine learning algorithms, and quick visualizations using your data [@www-coursera-python]. 

As Python has gained momentum with the Data Science field, another field in which the language is gaining ground is Big Data. Python is now compatible to work with the popular big data tool Hadoop [@www-whizlabs-com]. 

> "Python consists of Pydoop package which helps in accessing HDFS API and also writing Hadoop MapReduce programming. Besides that         Pydoop enables MapReduce programming to solve complex big data problems with minimal effort [@www-whizlabs-com]".

Python is also very scaleable within this environment. Another great component is that Python has a very large, robust user community that users can reach out to for guidance on all sorts of coding related topics. Due to the popularity of the language, experienced users are extremely willing to participate in the community to facilitate its growth and continued usage within the programming world.  

Python can be leveraged using a basic shell program, which can accomplish basic tasks, or with an interpreter or IDE (Integrated Developer Environments). An IDE is a dedicated program, integrated with several tools such as debuggers, build and execution tools, syntax highlighting, and source control tools, that are specifically used to writing software code [@www-realpython-com]. Some examples pf well known Python specific IDE programs are PyCharm, Spyder, and Thonny. When tasked with developing more sophisticated Python code for data science purposes, it is a good practice to use a dedicated code editor well suited to the task.  

In regards to working with Twitter, there is a Python library entitled Tweepy that can be installed along with any other required libraries and toolkits. Users will need to use the pip command at a terminal screen in order to install tweepy. PIP is a package management system used by Python to install and manage larger software packages [@www-en-wikipedia-pip]. Below is the installation code:

-- insert installation snippet

After installation is complete, users will need to use the import function to fully load the tweepy program into the python script that's in development.

-- insert import screenshot

The next step is authentication between the Twitter API and python. As mentioned earlier, there are 4 required keys needed for this step for which Tweepy is responsible for completing. Tweepy currently supports oauth authentication and authentication is handled via the tweepy AuthHandler class in python [@www-tweepy-io]. Oauth authentication is considered the standard method for token authentication by 3rd-party applications such as Facebook and Twitter. Oauth works on behalf of the end user to provide a token which authorizes specific information to be shared between applications [@www-searchmicroservices].  There are four variables in the python code that will be used to hold the security information

-- insert authentication piece

Once tweepy is set up and the user passes through the authentication step, users can now begin further development on python code that can be implemented against Twitter data.. Tweepy collects tweets in real-time, so the script will be collecting tweets that were released just prior, or during the implementation of the script. The tweepy program in Python can only collect 100 tweets at a time, so the script can be built to contain a function which runs in an iterative loop to collect a set number of tweets as defined by a 'MaxTweets' parameter. Once that parameter value is met, the function terminates. 

The requirements for this project are to run a python script to collect twitter data, specifically tweets with the hashtags #cats and #dogs. Next, is to store the twitter data within a MongoDB database using my local computer and also in the cloud using MongoDB. In order to pull twitter data, users must create a Twitter API account through the Twitter developers website. After creating an account, users wil be provided with four distinct security tokens that users will need in order to connect to the Twitter API through Python. 

Next, I installed the latest version of Python, which is version 3.7.1. Python is an open source general purpose programming language that is very useful for data science projects. There are numerous libraries available to install within Python that will help you accomplish your end goal. For this project, the primary library that I want to use for collecting twitter data is tweepy. Tweepy is designed to handle multiple aspects of twitter tweet collection including authentication, connection, session management, and reading and routing incoming messages [@www-tweepy-io]. 


## Data

For this term paper, I created a Twitter API account and used Python to connect to Twitter directly using a set of credentials that were supplied to me. Using a python script, I created two sets of data; one for tweets that contained the hashtag #dog and a second dataset that contained tweets with the hashtag #c .at. After the data is pulled, the json data is converted into dataframes using the pandas package. 

Twitter data, when extracted, is in JSON format. JSON (Javascript Object Notation) is a data interchange format that is both easy for humans to read and write, and easy for machines to parse and implement [@www-json-org]. A json object is basically a set of key value pairs ending contained within two braces. 

-- add JSON object image here 

A json array is essentially a collection of key values contained within two brackets

-- add JSON array image here

Twitter JSON data is comprised of many different components, all of which are used to describe individual tweets. 

>> "At Twitter we serve many objects as JSON, including Tweets and Users. These objects all encapsulate core attributes that describe      the object. Each Tweet has an author, a message, a unique ID, a timestamp of when it was posted, and sometimes geo metadata shared by    the user. Each User has a Twitter name, an ID, a number of followers, and most often an account bio [@www-developer-twitter]".

Below is an example of a tweet and a description of the content:

-- insert image of sample json twitter record

The tweets follow a parent-child construction. All tweets contain a user object which can also contain a geo-tagged child object describing the geographic location of where the tweet originated. The tweet also contains an entities object that consists of information such as assigned hashtags, URLs, user mentions, and any sort of media material [@www-developer-twitter]. The data record also contains a flag to indicate if the tweet has been retweeted, or has been forwarded by someone else to another person. A retweet is typically comprised of someone else's comments that a user would like to share.  

## Twitter Cloud Storage

There are many options available today to store twitter data within a cloud storage platform. Cloud storage consists of storing data within logical pools that can span multiple servers and multiple locations throughout many locations [@www-en-wikipedia-cloud]. Cloud services can be accessed through a dedicated cloud service platform, and website APIs such as cloud desktop storage and gateways. [@www-en-wikipedia-cloud].  Some of the main players in today's cloud computing market are Amazon Web Services, Microsoft Azure, and Google iCloud. The focus of this paper will be on the Amazon Web Services platform. 

Amazon Web Services (AWS) provides a portfolio of services that can help organizations deal with the voluminous amounts of data that's available in Twitter. AWS provides a cloud storage service called S3 which is capable of storing data of any type from a variety of sources including web sites, mobile apps, and even IoT sensors [@www-aws-amazon-s3]. Used in conjunction with Amazon Glacier, and Amazon Glue, one could build a secure data lake in the cloud that could be set up to contain streaming twitter data. Once the data is in the data lake, one can take advantage of cutting-edge advanced machine learning and analytics capabilities available through additional Amazon services such as AWS Athena (Interactive analytics), AWS Kinesis (Real-Time Analytics), and AWS Sagemaker and Deep Learning AMIs
[@www-was-amazon-s3].

-- insert AWS image here

A lot of organizations today leverage the power and scalability of the S3 platform and come to rely on the system for its day-to-day data needs. That reliability was tested during an S3 outage that occurred on February 27th, 2017 that effected Amazon's entire US-EAST-1 region. This outage caused widespread website outages and vast disruptions to Amazon's clients. The issue was caused by an Amazon employee typing an incorrect command which caused several key subsystems to go offline [@www-theverge-s3]. This was an embarassing incident for Amazon that just goes to show how important cloud services have become in recent years.  

In addition to the S3 platform, Amazon includes other services that allow users to set up and manage virtual machines and virtual cloud platforms. Users can create a cloud cluster leveraging one of these services and run a different database application that is more suitable to their data needs. MongoDB Atlas, an open source database storage system that provides support for JSON document style data, is one of those types of applications that can be stood up and managed on an Amazon Virtual Private Cloud (VPC). Mongo Atlas provides a platform from which users can create and manage their own clusters, as well as set up automation jobs to manage provisioning and deployment tasks [@www-mongodb-com]. Users are required to create an account with Mongo DB Atlas, which provides a minimum of 512 MB of storage for a free cloud database, but can be updated to 10 GB or more along with dedicated RAM, backups, and performance optimization with the creation of a dedicated cluster [@www-mongodb-com]. In addition to running on Amazon VPC, MongoDB Atlas can also run on Microsoft Azure and Google Cloud. 

Connecting to MongoDB Atlas from python is fairly straightforward and requires the pymongo python library to be installed. The pymongo library contains several tools that enables the user to connect to a MongoDB data, either on their local machine, or a database hosted on a MongoDB Atlas cluster. Users must use the pip method from a command prompt or terminal screen and run the following command:

-- insert pip command for pymongo installation

After the pip command is completed and pymongo is installed, the library must be imported into python using the following simple command:

-- insert import pymongo command

The Mongo Client component is one of the pymongo tools allowing for python to connect to a MongoDB database. Connecting to a local instance of MongoDB is simple and requires that the software is fully installed and the MongoDB service is up and running.Also, port 27017 must be available on your machine in order for the two applications to communicate properly. The python command for connecting to a local MongoDB instance is as follows:

-- insert mongoDB connection script to local machine

Connecting to a MongoDB Atlas cluster involves a few more steps. First, before you can start up a cluster, there are a few requirements that need to be met. Users must have the correct TLS/SSL support in place and be able to have the correct SNI driver installed in order to connect [@www-docs-mongodb-atlas]. Users must also add their IP address to the MongoDB Atlas Whitelist. This ensures that the only connections allowed will be listed in MongoDB's whitelist [@www-docs-mongodb-atlas]. Next, users must create a user account with Admin access in order to be able to administer the cluster. After those steps are complete, and the cluster has been started up, users must choose a connection method to use in order to connect to another application. The connection dialog contains different connection strings for different versions of applications including Java, C, C++, Perl, Ruby, and Python. To set up a connection between MongoDB Atlas and Python, users will need to select a URI connection string based on their version of Python. Next, they will need to paste that string within their python script within the following pymongo command:

-- insert mongoDB Atlas connection script image. 

After this is complete, and you're able to connect without any issues, you can begin to create databases, collect and insert data into the MongoDB database, as well as other data related tasks. Just a note on connecting to MongoDB, users will sometimes receive error messages pertaining to DNS connection errors. To resolve this, users need to install the dnspython library using the pip method and importing the resolver tool from the dnspython library within python. 

-- insert image of dnspython import string

Once fully connected to MongoDB, you begin to 'listen' or search for tweets that contain a specific word, phrase, user, #hashtag, or any other piece of information that you're interested in mining for. There's a couple of ways to set up the search criteria, but typically a variable is created that contains the search words such as listed below:

-- insert code samples for setting up variables, search words, count, periods.

You can configure tweepy to work in a search or streaming manner. Tweepy has a class entitled StreamListener that will access the Twitter API and pull all tweets are created using the specified criteria [@www-pythondata-twitter]. Once executed, the script will continue streaming until the script is stopped. 

MongoDB Atlas was designed to handle large datasets by spreading the data among many servers with the cloud computing platform [@www-mongodb-bigdata]. MongoDB can also be connected to a Hadoop instance to deal with the upcoming challenges that are presented by Big Data. This creates an ideal environment to house streaming Twitter data as MongoDB is perfect for document data types such as JSON. 

MongoDB Atlas can be provisioned to connect to other applications using different connection methods. 

## Data Science Algorithms for Twitter Data


   
## Visualizations

-- matplotlib, redash, MongoDB Compass



## Results

## Conclusion








