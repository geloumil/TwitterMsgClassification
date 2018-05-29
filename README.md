# TwitterMsgClassification
Classificating Tweets into positive, negative, neutral using Sentiment Analysis

<br>
<p><i>To view jupyter markdown cells follow:</p></i>
http://htmlpreview.github.io/?https://github.com/geloumil/TwitterMsgClassification/blob/master/TweetClassification.html

Contents
--------
<ol type="a">
  <li>Abstract</li>
  <li>Feature extraction</li>
  <li>Text Mining</li>
  <li>Classification Model Selection</li>
  <li>Sentiment Analysis</li>
  <li>Evaluating Results</li>
  </ol>  
  
a) Abstract
-----------
In the context of this implementation we are approaching tweeter messages analysis using:
<ol type="a">
<li>Known Classification Methods</li>
 <li>Sentiment Analysis using textblob</li>
</ol>

b)Feature extraction
--------------------
In order to train our ML algorithms to utilize given text data, there is a need to transform the raw documents(tweets)
into vectors. In addition to that we apply TF-IDF logic so as to find the importance of each word in the documents given.

c)Text Mining
--------------
<ul>
<li>Stop words (english) are removed, since they provide no significant information.</li>
<li>Spell check and lemmatization is attempted (the code is commented though since it introduces significal delay).</li>
<li>URLs are removed.</li>
<li>Digits are removed.</li>
<li>Punctuation is removed.</li>
</ul>

d)Classification Model Selection
---------------------------------
For the puprose of classifying tweets based on polarity, the following algorithms are selected:
<ul>
<li><p><b>Linear Gradient Descent</b> &rarr; works well for topic classification.</p></li>
<li><p><b>Random Forests</b> &rarr; simple and has prominent performance for high dimensional data.</p></li>
<li><p><b>Multinomial Naive Bayes</b> &rarr; works well on numeric and textual data +easy to implement.</p></li>
<li><p><b>KNN</b> &rarr; very good results and scales up well with the number of documents.</p></li>
<li><p><b>LinearSVC</b> &rarr; effective compared to supervised machine learning algorithms.</p></li>
</ul>

After training and evaluating which of the above performs the best in it's default version,
the hyper parameters of the best one are tuned in aim to produce even better results:
(Spoiler alert: Best one is Linear Support Vector Machine Classifier aka LinearSVC *** this is for the whole dataset,
 not in this sliced dataset example given***)

e)Sentiment Analysis
--------------------
The implementation so far was a plain classification attempt. Sentiment Analysis is now introduced, using TextBlob.
Similarly to the classification approach, multiple classifiers are trained, so as to select the one that behaves
in the best way.
(Spoiler alert they all have the same accuracy).

Algorithms Selected:
<ul>
<li><p><b>NaiveBayesClassifier.</b></p></li>
<li><p><b>DecisionTreeClassifier.</b></p></li>
<li><p><b>MaxEntClassifier</b> &rarr; provides robust results and it is competitive in terms of CPU and memory consumption.</p></li>
</ul>


f)Evaluating Results
--------------------
Accuracy of all algorithms:

  <strong>Linear Gradient Descent:</strong>        0.44<br>
  <strong>Random Forests:</strong>                 0.49<br>
  <strong>Multinomial Naive Bayes:</strong>        0.48<br>
  <strong>KNN:</strong>                            0.35<br>
  <strong>PassiveAggressive:</strong>              0.43<br>
  <strong>LinearSVC:</strong>                      0.44<br>
  <strong>Tuned LinearSVC:</strong>                0.84<br>

  <br><br>
  <strong>NaiveBayesClassifier</strong>           0.48<br>
  <strong>DecisionTreeClassifier</strong>         0.48<br>
  <strong>MaxEntClassifier</strong>               0.48<br>

<br><br><br><br>  
<p><i>Information used for algorithm selection:</i></p>
http://www.jait.us/uploadfile/2014/1223/20141223050800532.pdf<BR>
http://blog.datumbox.com/machine-learning-tutorial-the-max-entropy-text-classifier/
