


# Datasets {#data}
Throughout the book, all models and techniques are applied to real datasets that are freely available online.
We will use different datasets for different tasks:
Classification, regression and text classification.

## Bike Rentals (Regression) {#bike-data}
This dataset contains daily counts of rented bicycles from the bicycle rental company [Capital-Bikeshare](https://www.capitalbikeshare.com/) in Washington D.C., along with weather and seasonal information.
The data was kindly made openly available by Capital-Bikeshare.
Fanaee-T and Gama (2013)[^Fanaee] added weather data and season information.
The goal is to predict how many bikes will be rented depending on the weather and the day.
The data can be downloaded from the [UCI Machine Learning Repository](http://archive.ics.uci.edu/ml/datasets/Bike+Sharing+Dataset).


New features were added to the dataset and not all original features were used for the examples in this book.
Here is the list of features that were used:

- Count of bicycles including both casual and registered users.
The count is used as the target in the regression task.
- The season, either spring, summer, autumn or winter.
- Indicator whether the day was a holiday or not.
- The year, either 2011 or 2012.
- Number of days since the 01.01.2011 (the first day in the dataset).
This feature was introduced to take account of the trend over time.
- Indicator whether the day was a working day or weekend / holiday.
- The weather situation on that day. One of:
    - clear, few clouds, partly cloudy, cloudy
    - mist + cloudy, mist + broken clouds, mist + few clouds, mist
    - light snow, light rain + thunderstorm + scattered clouds, light rain + scattered clouds
    - heavy rain + ice pallets + thunderstorm + mist, snow + fog
- Temperature in degrees Celsius.
- Relative humidity in percent (0 to 100).
- Wind speed in km per hour.


For the examples in this book, the data has been slightly processed.
You can find the processing R-script in the book's [Github repository](https://github.com/christophM/interpretable-ml-book/blob/master/R/get-bike-sharing-dataset.R) together with the [final RData file](https://github.com/christophM/interpretable-ml-book/blob/master/data/bike.RData).


## YouTube Spam Comments (Text Classification) {#spam-data}
As an example for text classification we work with 1956 comments from 5 different YouTube videos.
Thankfully, the authors who used this dataset in an article on spam classification made the data  [freely available](http://dcomp.sor.ufscar.br/talmeida/youtubespamcollection/) (Alberto, Lochter, and Almeida 2015[^Alberto]).

The comments were collected via the YouTube API from five of the ten most viewed videos on YouTube in the first half of 2015. 
All 5 are music videos.
One of them is "Gangnam Style" by Korean artist Psy. 
The other artists were Katy Perry, LMFAO, Eminem, and Shakira.


Checkout some of the comments. 
The comments were manually labeled as spam or legitimate.
Spam was coded with a "1" and legitimate comments with a "0".


|CONTENT                                                                                                                                                                | CLASS|
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----:|
|Huh, anyway check out this you[tube] channel: kobyoshi02                                                                                                               |     1|
|Hey guys check out my new channel and our first vid THIS IS US THE  MONKEYS!!! I'm the monkey in the white shirt,please leave a like comment  and please subscribe!!!! |     1|
|just for test I have to say murdev.com                                                                                                                                 |     1|
|me shaking my sexy ass on my channel enjoy ^_^                                                                                                                         |     1|
|watch?v=vtaRGgvGtWQ   Check this out .                                                                                                                                 |     1|
|Hey, check out my new website!! This site is about kids stuff. kidsmediausa  . com                                                                                     |     1|
|Subscribe to my channel                                                                                                                                                |     1|
|i turned it on mute as soon is i came on i just wanted to check the  views...                                                                                          |     0|
|You should check my channel for Funny VIDEOS!!                                                                                                                         |     1|
|and u should.d check my channel and tell me what I should do next!                                                                                                     |     1|

You can also go to YouTube and take a look at the comment section.
But please do not get caught in YouTube hell and end up watching videos of monkeys stealing and drinking cocktails from tourists on the beach.
The Google Spam detector has also probably changed a lot since 2015.

[Watch the view-record breaking video "Gangnam Style" here](https://www.youtube.com/watch?v=9bZkp7q19f0&feature=player_embedded).

If you want to play around with the data, you can find the [RData file](https://github.com/christophM/interpretable-ml-book/blob/master/data/ycomments.RData) along with the [R-script](https://github.com/christophM/interpretable-ml-book/blob/master/R/get-SpamTube-dataset.R) with some convenience functions in the book's Github repository.

## Risk Factors for Cervical Cancer (Classification) {#cervical}

The cervical cancer dataset contains indicators and risk factors for predicting whether a woman will get cervical cancer.
The features include demographic data (such as age), lifestyle, and medical history.
The data can be downloaded from the [UCI Machine Learning repository](https://archive.ics.uci.edu/ml/datasets/Cervical+cancer+%28Risk+Factors%29) and is described by Fernandes, Cardoso, and Fernandes (2017)[^Fernandes].

The subset of data features used in the book's examples are:

- Age in years
- Number of sexual partners
- First sexual intercourse (age in years)
- Number of pregnancies
- Smoking yes or no
- Smoking (in years)
- Hormonal Contraceptives yes or no
- Hormonal Contraceptives (in years)
- Intrauterine device yes or no (IUD)
- IUD Number of years with an intrauterine device (IUD)
- Has patient ever had a sexually transmitted disease (STD) yes or no?
- Number of STD diagnoses
- Time since first STD diagnosis
- Time since last STD diagnosis
- The Biopsy results "Healthy" or "Cancer". Target outcome.

The biopsy serves as the gold standard for diagnosing cervical cancer.
For the examples in this book, the biopsy outcome was used as the target.
Missing values for each column were imputed by the mode (most frequent value), which is probably a bad solution, since the true answer could be correlated with the probability that a value is missing.
There is probably a bias because the questions are of a very private nature.
But this is not a book about missing data imputation, so the mode imputation will have to suffice for the examples.

To reproduce the examples of this book with this dataset, find the
[preprocessing R-script](https://github.com/christophM/interpretable-ml-book/blob/master/R/get-cervical-cancer-dataset.R) and the 
[final RData file](https://github.com/christophM/interpretable-ml-book/blob/master/data/cervical.RData) in the book's Github repository.

[^Fanaee]: Fanaee-T, Hadi, and Joao Gama. 2013. “Event Labeling Combining Ensemble Detectors and Background Knowledge.” Progress in Artificial Intelligence. Springer Berlin Heidelberg, 1–15. doi:10.1007/s13748-013-0040-3.

[^Alberto]: Alberto, Túlio C, Johannes V Lochter, and Tiago A Almeida. 2015. “Tubespam: Comment Spam Filtering on Youtube.” In Machine Learning and Applications (Icmla), 2015 Ieee 14th International Conference on, 138–43. IEEE.

[^Fernandes]: Fernandes, Kelwin, Jaime S Cardoso, and Jessica Fernandes. 2017. “Transfer Learning with Partial Observability Applied to Cervical Cancer Screening.” In Iberian Conference on Pattern Recognition and Image Analysis, 243–50. Springer.