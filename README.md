# Anomaly_detection_using_ML

## Introduction
**Anomaly detection** also known as outlier detection is a data mining process used to determine types of anomalies found in a dataset and to determine details about their occurrences. Automatic anomaly detection is critical in today’s world where the sheer volume of data makes it impossible to tag outliers manually. Auto anomaly detection has a wide range of applications such as fraud detection, system health monitoring, fault detection, and event detection systems in sensor networks, and so on.

### Motivation
I was curious to see how different unsupervised ML algorithms (K-means clustering, Isolation Forest, One Class SVM, Gaussian Distribution) identify anomalies in a dataset.

### Data
I used a dataset from <a href=https://www.expedia.com>Personalize Expedia Hotel Searches</a>, which can be found <a href=https://www.kaggle.com/c/expedia-personalized-sort/data>here</a>.

For a simplicity of the analysis I selected:
* train.csv;
* one single hotel, which has the largest number of data points (prop_id = 124342);
* visitor_location_country_id = 219;
* search_room_count = 1;
* key features for the analysis: date_time, price_usd, srch_booking_window, srch_saturday_night_bool.

## Getting started
You need an installation of Python, plus the following libraries:

* numpy
* pandas
* matplotlib.pyplot
* seaborn
* sklearn

## Summary and key findings
The price anomaly detection was done using 4 different methods (K-means clustering, Isolation Forest, One Class SVM, Gaussian Distribution). It is clear that the methods provide different results such as:
* With K-means clustering approach anomalies are found for apartments with ~ midium and high range of prices;
* The anomalies range for Isolation Forest technique belongs to both mid and high ranges of price for a rent. However, Isolation Forest techniques gives more anomalies in a higher range of prices than k-means clustering;
* With One Class SVM we could find anomalies for low, mid and high price ranges of a rent. Moreover, this is the only method which gives anomalies for a low range prices;
* With Gaussian Distribution method we got outliers in the upper range of price, while for other techinques we got a distribution of outliers within different ranges.

After building the models, we have no idea how well it is doing as we have nothing to test it against. Hence, the results of those methods need to be tested in the field before placing them in the critical path.
