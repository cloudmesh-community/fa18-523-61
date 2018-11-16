# Natural Language Applications and Challenges within Big Data :hand: fa18-523-61

| Jay Stockwell
| jaystock@iu.edu
| Indiana University
| hid: fa18-523-61
| github: [:cloud:](https://github.com/cloudmesh-community/fa18-523-61/edit/master/paper/paper.md)


* :o: this is a draft, review has not been started due to this


---
Keywords : Natural Language Processing, Deep Learning, SyntaxNet, Part of Speech tagging
---

## Abstract

This paper examines Natural Language Processing (NLP), the current challenges facing NLP, and its usage within Big Data today.  Organizations have recently begun to harness the immense power of big data and how the concept can prove to be a beneficial component.  The term big data used to be a scary term that elicited feelings of consternation and anxiety, but with organizations experiencing exponential growth in data volume, the term has become mainstream and widely accepted.  Big data is largely unstructured text and constantly in a state of enormous growth, which is why NLP offers many opportunities to tap into this vast data resource [@www.expertsystem]. This paper will explore the evolving, and sometimes challenging relationship between NLP and Big Data, the problems that NLP can solve, which applications are leveraged, and how the data can be transformed into a presentable format for consumption. 

## Introduction

Big data “describes the growing volume of structured and unstructured, multi-source information that is too large for traditional applications to handle [@www.expertsystem].”  The volume of today’s data is on an unprecedented growth trajectory due to the ample methods to collect and analyze data. The Internet of Things, mobile devices, sensors, cameras, and software logs are just some examples of non-traditional methods of data collection are contribute to the abundance of information today [@hid-sp18-516-www-wiki-bigdata]. There’s no end in sight to exponential growth that is projected over the next several years. According to Wikipedia: 

> "The world's technological per-capita capacity to store information has roughly doubled every 40 months since the 1980s;[11] as of       2012, every day 2.5 exabytes (2.5×1018) of data are generated.[12] Based on an IDC report prediction, the global data volume will       grow exponentially from 4.4 zettabytes to 44 zettabytes between 2013 and 2020.[13] By 2025, IDC predicts there will be 163 zettabytes   of data" [@hid-sp18-516-www-wiki-bigdata].
    
Natural Language Processing is a relatively new concept and is gaining momentum in the use of text analysis and presentation.  Elizabeth Liddy from Syracuse University provides a great definition:

> "Natural Language Processing is a theoretically motivated range of computational techniques for analyzing and representing naturally     occurring texts at one or more levels of linguistic analysis for the purpose of achieving human-like language processing for a range     of tasks or applications" [@www-surface-syr-edu].

Essentially NLP’s goal is to achieve a level of text analysis and processing that mimicks very closely the way that humans process language.  While NLP has truly made significant progress over the last several years, the challenge of deciphering the exact context and inference of text is still an area of which NLP is still improving [@www-surface-syr-edu].

## Natural Language Challenges

As previously mentioned, there are many challenges that face NLP today. Some of the challenges pertain to how NLP parses sentences, deals with cultural differences, language translation, conversational issues (ie. whether the statement is a question or answer), and sentiment. In order for NLP to function in an effective manner within Big Data, there needs to be a process set in place to assist with these issues. 

Parsing, the ability to deconstruct a sentence into its parts, is a major challenge facing NLP. Parsing can lead to ambiguity because it can be difficult to detect the correct syntax, and/or the exact interpretation of each word. Prepositions within a sentence can cause confusion because it can be hard to determine which word is being modified. as explained by Armando Viera and Bernadete Ribeiro:

> "..the sentence "Alice drove down the street in her car" has at least two possible dependency parses. The first corresponds to the       (correct) interpretation where Alice is driving in her car; the second corresponds to the (absurd but possible) interpretation where     the street is located in her car. The ambiguity arises because the preposition in can modify either drove or street.                     [@Natural-Language-Speech]."

Part of Speech tagging is another NLP concern. Part of speech tagging is the process of assigning a part of speech definition to a word within a sentence.[@www-language-worldofcomputing]. Common parts of speech include nouns, verbs, adjectives, and adverbs. Challenges can arise due to the lack of context. There are many words that have multiple meanings, which can lead to ambiguity when computers try to assign a descriptor. For example, the word chair can have multiple meanings; you can chair(verb) or lead a meeting, or you can sit in a chair (noun) [@www-language-worldofcomputing]. 

Another challenge is Natural Language Understanding (NLU). NLU pertains to the ability of a computer to comprehend the sentence structure and intended meaning of human languages, which in turn allows humans to fully communicate and interact with machines using real sentences [@www-gartner-nlu]. This concept is gained interest in recent years due to the many possible ways this can be leveraged within applications on a commercial scale.  

> "There is considerable commercial interest in the field because of its application to question answering,[3] 
  news-gathering, text categorization, voice-activation, archiving, and large-scale content analysis [@www-en-wikipedia-nlu]."
  
With the rise of Artificial Intelligence (AI), NLU has risen in complexity due to the extraordinary computations involved.   
The concept is considered one of the most challenging problems in the AI world. These types of problems require intense computational effort and also require human intervention and resources as they cannot be solved by machines alone. Challenging AI problems are known as AI-Hard or AI-complete.

> "In the field of artificial intelligence, the most difficult problems are informally known as AI-complete or AI-hard, implying that     the difficulty of these computational problems is equivalent to that of solving the central artificial intelligence problem—making       computers as intelligent as people, or strong AI.[1] To call a problem AI-complete reflects an attitude that it would not be solved by   a simple specific algorithm [@www-en-wikipedia-aihard]." 

In order to NLU to properly function, machines must be programmed to understand text. NLU must follow all the text translation rules that any human would follow if they were reading through any type or text document. Machines must have the ability to mimick human abilities and human intellectual skills such as reason, common sense, and intuition that relate to how humans perceive language and social intelligence concepts [@www-en-wikipedia-aihard]. NLU requires an enormous amount of work in order to prove effective. NLU applications require extensive data gathering and subject matter investigation and research in order to properly train the system to perform [@www-info-contactsolutions].

## Natural Language Processing Solutions

There are some solutions in place to address the challenges facing NLP. With respect to the parsing problem, there is a relatively new concept designed by Google called SyntaxNet. SyntaxNet is based on the TensorFlow open source library readily available to users for designing deep learning models. With SyntaxNet, Google employed a normalized neural network model that provides an output of possible syntactical possibilities or hypotheses given a group of words [@Natural-Language-Speech]. SyntaxNet runs the model multiple times and discards hypotheses that are ranked lower and appear to be unlikely candidates. As far as parsing, SyntaxNet has developed a reputation for being the best parser, being known to sometimes exceed human accuracy, and recently made available in 40 languages.  [@Natural-Language-Speech]. 

The latest version of SyntaxNet can be trained against a separate data set, and individuals have a good deal of freedom in tweaking the parameters of the model to better fit the particular nuances of their datasets. SyntaxNet includes a model built specifically for the English language entitled Parsy McParseface and acn be used to analyze English texts right out the box [@ai-googleblog.com].

Members of the Stanford University's Natural Language Processing Group has developed a part of speech tagger that works remarkably well. The application runs on Java and is somewhat memory intensive, requiring upwards of 60-200 Mb of memory to function efficiently, with around 1 Gb recommended in order to train a dataset [@www-stanford-nlpgroup]. ( information here about Bidirectional Network..)The latest download contains three distinct tagger models for the English Language as well as an Arabic, German, Chinese, and French model. These models can be retrained on any language. During an experiment against Penn Treebank WSJ data, the Stanford POS tagger returned an impressive per-position tag accuracy of 97.24% [@www-stanford-csd]. 

As NLU continues to become more mainstream, many companies are embedding proprietary NLU algorithms within their products to further enhance their overall NLP capabilities. Some of the companies and their associated applications are Apple (Siri), Google(GoogleNow, Google Search), Microsoft(Cortana), and IBM (Watson, DeepQA) [@www-info-contactsolutions]. These products are just the beginning of a new wave of technology that will surely influence how organizations incorporate NLP into their business processes.  

In order for NLP to succeed, it needs to be trained against very large datasets or corpuses. A corpus is a collection of written texts used for research or investigation purposes. Two examples of widely used corpuses are: 

> "The Google n-gram corpus, a trillion word database containing phrases (up to 5 words long) occurring on public Web pages. The USENET   corpus, a 25 billion word (compressed) corpus containing public USENET postings on 47,680 English language, non-binary-file newsgroups   between Oct 2005 and Jan 2010 [@www-cloudera-blog]."

In order to write effective programs against such large big data sets, a new platform has been developed entitled Natural Language Toolkit (NLTK). The platform is completely open source and supported by a strong community of users. Users can leverage the platform to build applications using the Python programming language. NLTK provides user with a simplistic interface that can access over 50 different corpora data sets linguistic and lexical data resources [@www-nltk-org]. Users can also leverage several built-in libraries for classification, tokenization, tagging, parsing, semantic reasoning, and powerful wrappers to utilize with NLP libraries [@www-nltk-org].  NLTK comes with a comprehensive learning guide to assist users, specifically those with little to no Python experiense, to get up to speed with the various syntax commands that are used within NLP. 

Some organizations leverage Hadoop, an open source processing framework that works extremely well against very large textual datasets that require enormous amounts of computational power. Hadoop can also act as a data management application providing massive storage space and can handle numerous concurrent processing tasks. Hadoop's ability to work with various kinds of structured and unstructured data make it an ideal application for NLP, as it can handle an exorbitant amount of data from sources such as internet clickstream records, web server application logs, social media sites such as facebook and twitter, customer emails, and sensor information from the internet of things [@www-searchmdatamanagement-hadoop].  The aforementioned deep learning algoritms can be set up to run in a Hadoop environment to leverage its extraordinary size and computational power.

In recent years, with the precipitous rise of data science and the use of algorithms for predictive analysis among other areas, one concept in particular, Deep Learning, has emerged as a possible solution to answering some of the aforementioned challenges facing NLP. 

> "Deep learning (DL) has had a tremendous impact on natural language processing (NLP). After image and audio, probably this is the area   where DL has unleashed the most transformative forces. For example, almost all projects related to NLP at Stanford University, one of   the most respected institutions working on this area, involve DL research [@Natural_Language_Speech]."

Deep learning, or Deep Neural Networks as it is sometimes referred to, is a branch of AI. The neural networks go through a series of tranformation steps on the inputted data and leverages the what it learns to build a comprehensive statistical model [@www-searchenterpriseai-com]. The model will continue to run through a series of iterations until it returns an acceptable level of accuracy. Deep learning algorithms can be trained against big data sets just like other standard algorithms and have proven to be effective in this manner. For example, "Trained on movie subtitles, language models are able to generate basic answers to questions about object colors or facts [@Natural_Language_Speech].  Deep Learning networks can be coded using the NLTK and Hadoop platforms mentioned above to tackle the numerous challenges facing NLP today. 

## Conclusion

In conclusion, the NLP field has proven its importance in the data world by allowing for entities to analyze and evaluate many aspects of the components of language. The challenges that have arisen from leveraging NLP such as parsing and part of speech tagging have beem met with the development of new applications such as Google's SyntaxNet and Stanford's Part of Speech tagger.  Since NLP is still in it's early stages, there will continue to be new challenges, and just like SyntaxNet, new applications will meet these challenges and make NLP even more effective. These applications leverage algorithms such as neural networks and deep learning to facilitate the effective training of datasets. Today's organizations deal with, and store enormous amounts of textual data from many different sources. Because this information is comprised of primarily language, organizations that leverage big data and work with this type of data are starting to understand the implications that NLP provides in evaluating their growing stores of data to detect patterns, connections and trends within their various data sources [@www-expertsystems-nlp]. Big data storage has become easier to manage due to new open source database management systems such as Hadoop. The volume of NLP data will continue to grow exponentially and new processing and storage management technologies will need to be designed to be not only scaleable, but have the capacity to work with the ever changing business demands. NLP will continue to grow and we need to be ready to meet the new challenges that an emerging technology presents.  





