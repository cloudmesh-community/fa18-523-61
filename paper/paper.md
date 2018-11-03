## Natural Language Applications and Challenges within Big Data - :smiley: fa18-523-61

:o: format incorrect

| github: [:cloud:](https://github.com/cloudmesh-community/fa18-523-61/edit/master/paper/paper.md)


## Abstract

   This paper examines Natural Language Processing (NLP), the current challenges facing NLP, and its usage within Big Data today.  Organizations have recently begun to harness the immense power of big data and how the concept can prove to be a beneficial component.  The term big data used to be a scary term that elicited feelings of consternation and anxiety, but with organizations experiencing exponential growth in data volume, the term has become mainstream and widely accepted.  Big data is largely unstructured text and constantly in a state of enormous growth, which is why NLP offers many opportunities to tap into this vast data resource [@www.expertsystem]. This paper will explore the evolving, and sometimes challenging relationship between NLP and Big Data, the problems that NLP can solve, which applications are leveraged, and how the data can be transformed into a presentable format for consumption. 

## Introduction:

   Big data “describes the growing volume of structured and unstructured, multi-source information that is too large for traditional applications to handle [@www.expertsystem].”  The volume of today’s data is on an unprecedented growth trajectory due to the ample methods to collect and analyze data. The Internet of Things, mobile devices, sensors, cameras, and software logs are just some examples of non-traditional methods of data collection are contribute to the abundance of information today [@en.wikipedia]. There’s no end in sight to exponential growth that is projected over the next several years. According to Wikipedia: 

> "The world's technological per-capita capacity to store information has roughly doubled every 40 months since the 1980s;[11] as of       2012, every day 2.5 exabytes (2.5×1018) of data are generated.[12] Based on an IDC report prediction, the global data volume will       grow exponentially from 4.4 zettabytes to 44 zettabytes between 2013 and 2020.[13] By 2025, IDC predicts there will be 163 zettabytes   of data" [@en-wikipedia].
    
   Natural Language Processing is a relatively new concept and is gaining momentum in the use of text analysis and presentation.  Elizabeth Liddy from Syracuse University provides a great definition:

> "Natural Language Processing is a theoretically motivated range of computational techniques for analyzing and representing naturally     occurring texts at one or more levels of linguistic analysis for the purpose of achieving human-like language processing for a range     of tasks or applications" [@surface.syr.edu].

Essentially NLP’s goal is to achieve a level of text analysis and processing that mimicks very closely the way that humans process language.  While NLP has truly made significant progress over the last several years, the challenge of deciphering the exact context and inference of text is still an area of which NLP is still improving [@surface.syr.edu].

## Natural Language Challenges

As previously mentioned, there are many challenges that face NLP today. Some of the challenges pertain to how NLP parses sentences, deals with cultural differences, language translation, conversational issues (ie. whether the statement is a question or answer), and sentiment. In order for NLP to function in an effective manner within Big Data, there needs to be a process set in place to assist with these issues. 

Parsing, the ability to deconstruct a sentence into its parts, is a major challenge facing NLP. Parsing can lead to ambiguity because it can be difficult to detect the correct syntax, and/or the exact interpretation of each word. Prepositions within a sentence can cause confusion because it can be hard to determine which word is being modified. as explained by Armando Viera and Bernadete Ribeiro:

> "..the sentence "Alice drove down the street in her car" has at least two possible dependency parses. The first corresponds to the       (correct) interpretation where Alice is driving in her car; the second corresponds to the (absurd but possible) interpretation where     the street is located in her car. The ambiguity arises because the preposition in can modify either drove or street.                     [@Natural_Language_Speech]."

Part of Speech tagging is another NLP concern. Part of speech tagging is the process of assigning a part of speech definition to a word within a sentence.[@www-language-worldofcomputing]. Common parts of speech include nouns, verbs, adjectives, and adverbs. Challenges can arise due to the lack of context. There are many words that have multiple meanings, which can lead to ambiguity when computers try to assign a descriptor. For example, the word chair can have multiple meanings; you can chair(verb) or lead a meeting, or you can sit in a chair (noun) [@www-language-worldofcomputing]. 

Another challenge is Natural Language Understanding or translation (NLT). This concept is gained interest in recent years due to the many possible ways this can be leveraged within applications on a commercial scale. 

> "There is considerable commercial interest in the field because of its application to question answering,[3] 
  news-gathering, text categorization, voice-activation, archiving, and large-scale content analysis [@www-en-wikipedia-nlp]."
  
With the rise of Artificial Intelligence (AI), NLT has risen in complexity due to the extraordinary computations involved.   
The concept is considered one of the most challenging problems in the AI world. These types of problems require intense computational effort and also require human intervention and resources as they cannot be solved by machines alone. 

> "In the field of artificial intelligence, the most difficult problems are informally known as AI-complete or AI-hard, implying that     the difficulty of these computational problems is equivalent to that of solving the central artificial intelligence problem—making       computers as intelligent as people, or strong AI.[1] To call a problem AI-complete reflects an attitude that it would not be solved by   a simple specific algorithm [@www-en-wikipedia-aihard]." 

In order to NLT to properly function, machines must be programmed to understand text. NLT must follow all the text translation rules that any human would follow if they were reading through any type or text document. Machines must have the ability to mimick human abilities and human intellectual skills such as reason, common sense, and intuition that relate to how humans perceive language and social intelligence concepts [@www-en-wikipedia-aihard].

In recent years, with the precipitous rise of data science and the use of algorithms for predictive analysis among other areas, one concept in particular, Deep Learning, has emerged as a possible solution to answering some of the aforementioned challenges facing NLP. 

> "Deep learning (DL) has had a tremendous impact on natural language processing (NLP). After image and audio, probably this is the area   where DL has unleashed the most transformative forces. For example, almost all projects related to NLP at Stanford University, one of   the most respected institutions working on this area, involve DL research [@Natural_Language_Speech]."

Deep learning algorithms can be trained against big data sets just like other standard algorithms and have proven to be effective in this manner. For example, "Trained on movie subtitles, language models are able to generate basic answers to questions about object colors or facts [@Natural_Language_Speech]."  






