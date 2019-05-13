# Yelp_Rating_Predictor
Using the publicly available Yelp ratings dataset (8GB in size) is it possible to predict the Yelp ratings of a restaurant given it's location, category of food and hours its open. This project utilized the Apache Spark framework to clean the data and several machine learning algorithms were used to predict Yelp rating.

## Data Wrangling and Cleaning Process:

The JSON formatted data from Yelp was first transformed into a CSV file using Spark's dataframe API. The CSV file was then cleaned and filtered further using Spark's RDD map, filter and reduce methods. There over 300+ food categories these were grouped into more general categories like ( Fast Food, Chinese, Indian etc...). This was done to make the machine learning classification algorithims have less labels that overlap for certain features. These categories were then encoded as either 1 or 0 if they were tagged in the JSON for a specific resturant, again this was done to make the classification analysis simpler.

## Machine Learning Analysis:

The classification algorithims used for this analysis were SVM, Logistic Regression and Bernoulli Naive Bayes ( works with boolean features, like the encoded categories ). All of these algorithims produced similar accuracy level around 25% ( better measure would have been precision and recall to see how the different classes were predicted). To help determine the best features to predict Yelp Ratings an Extra Trees Classifier was used to do a feature importance analysis. The results showed that the city, hours of operation and the address of the resturant are more important than the actual category of the food the resturant serves.

<img width="676" alt="Screen Shot 2019-05-05 at 9 35 51 PM" src="https://user-images.githubusercontent.com/42993708/57205731-cd736e00-6f7d-11e9-8e7a-1c8c362b9266.png">
