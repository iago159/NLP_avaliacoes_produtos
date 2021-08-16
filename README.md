# Natural Language Processing: Reviews in portuguese

## About

Using a dataset containing the review text and the rating of a product, this project creates a machine learning model able to predict whether a given review is a bad or good review.

Furthermore, this project also approach 2 very used technics on text classification: Stemming and Stopwords. The "stemming" is the transformation of a word into a root word, while "stopwords removal" is the removal of words that appear in the text and have no relevant meaning.

At the end, the project compare the accuracy of reviews texts with: no stopword removal and no stemming, only stopword removal, only stemming and stopword removal and stemming.

## Data Cleaning

### Drop NaN
The start data had 84991 rows and 2 columns: review_text and rating (1 - 5), where 1 row has NaN value at 'review_text' field and therefore has been dropped.

### Clean field 'review_text'
- Convert to lowercase
- Strip ponctuation, linebreak, tabulations, multiple whitespaces, accents
- Create column 'sentiment' (score greater than or equal to 4: 'positivo', less than or equal to 3: 'negative')

## Distribute positive and negative reviews evenly
At first there were 66816 positive sentiments and 18174 negative sentiments. When evenly distributed, there were 18174 positive and negative reviews, totaling 36348 rows.

## Stopwords removal and stemming
The field 'review_text' was used to create the columns 'review_text_stopworded',	'review_text_stemmed' and	'review_text_stopworded_stemmed'

## The model
The model was build using the library scikit-learn, specificly the features 'train_test_split', 'CountVectorizer' and the 'LogisticRegression' model.

## Scores:

  | Review Text | Positive accuracy (%) | Negative accuracy (%) | Mean accuracy (%) |
  | :---         |     ---: |          ---: |     ---: |
  | No stopword removal - No stemming | 81.428 | 81.212 | 81.320 |
  | Stopworded | 81.206 | 80.882 | 81.045 |
  | Stemmed | 80.686 | 79.993 | 80.316 |
  | Stopword removal and Stemmed | 79.896 | 79.550 | 79.725 |
- The mean accuracy is made based in a more precised negative and positive accuracy

## Discussing

  In this project, using Brazilian Portuguese the most accurate model was the one using no stopwords removal and no stemming, reaching 81.32% of precision, while the less accurate was the one using both stopwords removal and stemming, with 79.73% of accuracy. The difference between them is more than 1.5%, thus in this case would be preferable use no stopword removal and no stemming.
