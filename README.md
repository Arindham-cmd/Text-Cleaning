# Text-Cleaning

I have choosen Bubmle Application Reviews as my task. Here, I have showcased step by step process that is involved for textual data analysis. 

The steps are to first take the textiual data from review column and make it into a list so that you can see all the necessary things that has to be changed and observed.

After that you start the processing work, for example to make the sentences into a lower case.Post that remove special charachters,emojis and punctuations. Then remove the stop words and after completing all the above steps then we do the tokenization and later anything between stemming or lemmatization. 

Then for analysis you can go ahead with ngram or can build a word cloud depending on the need.

Writing down Steps in bullet point format for clear understanding. 

1. Import the libraries initially (pandas, numpy, re). 
2. Load the dataset. 
3. Review the data.head() then drop the redundant features. 
4. Checking for missing records. 
5. Fill the missing records accordingly or can also drop the records if needed. 

6. check the feature that has the textual content, if it is a review then you can go ahead with below code

 for index,text in enumerate(data['content']):
   print('Review %d:\n'%(index+1),text)

              or
              
 ' '.join(data['content'].tolist())    ----> this line of code is majorly used. If the textual content records is too large then I would suggest to do this in a seperate notebook as doing in the same notebook will make the size too large. 

7. Check the number(len) of wordcount, special charachter and stop words each textual record contains. 
8. If you want to see what are those words in specific then you can just remove the "len" function from the command line and you will see the list of words,
   list of special charachters and list of stop wrods each record has. 
   
9. Now comes the processing work. 
10. First thing is we need to make all the statements look uniform, that is we need to make them in lower case first. 
11. Remove the punctuation, nubers, special charachters and emojis from the records. 
12. Now, lets remove the stop words from our text data. 
      To remove the stop words, we need to import library ---> 
      from nltk.corpus import stopwords
      stop = stopwords.words('english')
13. Next thing which we can do is check for spelling mistakes, I had used textblob library. Which had helped me to rectify to spelling errors but at same time
    it has also changed the already correct spellings to a meaningless word and that showcases the efficienccy of the library. However, In many cases if the data       has lot of spelling errors then it can be useful and also a point to note that there are other libraries as well like cleantext which we can use to check the 
    spelling errors. Anyways, I had used it to display on how we can use that library but dropped it later as it was affecting the efficiency. 
14. Coming to three major pillars of textual pre processing. 
    1. Tokkenization. -> Tokkenization will divide the sentence into sequnce of words.
    2. Stemming. -> Stemming will remove the suffices from words, for example it will remove 'ing','ly' and tries to get to the root word.
    3. Lemmatization. -> Lemmatization, Lemmatization is also similar like Stemming but there are many instances where Lemmatization outnumbers stemming in         
       efficiency and that is the reason we prefer Lemmatization.
15. Libraries for tokkenization - 
    import nltk
    from nltk.tokenize import WhitespaceTokenizer
16. libraries for stemming -
    #First we will import the library
    from nltk.stem import PorterStemmer       --> we can also use other library lilke snowballstemmer
    st = PorterStemmer()
17. libraries for Lemmatization - 
     from textblob import Word

18. We will plot our analysis
    We can use wordcloud
    from wordcloud import WordCloud
    import matplotlib.pyplot as plt
19. Then if you feel that there are words that bring no insights to your analysis then you can add those words in the stop words list. 
     
     from nltk.corpus import stopwords
stop = stopwords.words('english')
morestopwords = ['bumble','dating app','match']
stop.extend(morestopwords)

20. Then, do the ngram for more analysis to get different aspect of analysis. 
    
