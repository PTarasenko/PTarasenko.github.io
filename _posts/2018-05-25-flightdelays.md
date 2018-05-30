---
title: "Flight Delays for Air Traffic Controllers"
date: 2018-05-28
#tags: [machine learning, data science, classification]
#header:
#  image: "/images/flightdelays/plane1.jpg"
#excerpt: "Machine Learning, Flight Delays, Data Science"
mathjax: "true"
---
<img src="/images/flightdelays/plane.jpg">

<font size="3">Now days is very important for the Air Traffic Controllers to be more efficient in organizing ground servicing in airports. With knowing about upcoming delays on arrival, they can plan their ground servicing at airdrome in more productive way. For example they could start work with another aircraft during that time.</font>
<p>
<p>
<font size="3">My question was if I could use only static information that was given to Air Traffic Controllers before the flight to predict flight delays and their length on arrival. The data I was working with was taken from "Bureau of Transportation Statistic" for January 2018. And I was focusing only on Domestic Flight in USA. Total records for this month I got around 550,000.</font>
<p>
<font size="3">During this project I worked with <b>Classification</b> problem to predict if delay going to happen. Also <b>Regression</b> problem and <b>Multi Classification</b> problems to predict length of delay. 
<p>
<p>
<b>On this graph we can see how many delays and their length each Aircompany have</b>
<p>
<img src="/images/flightdelays/del1.png">
<p>
<p>
<b>Interesting thing that length of delays on departure longer than delays on arrival</b>
<p>
<img src="/images/flightdelays/del2.png">
<p>
<font size="3"><b>The features that I decided to focus for prediction flight delays are:</b>
<br>
<font size="3">1. <b>Day of the week:</b> Day of the flight departure (Mon - Sun)
<br>
<font size="3">2. <b>Airline Code:</b> Short name of Air Company. In total was 18 Air companies recorded during that month.
<br>
<font size="3">3. <b>Tail Number:</b> It is like plate number on a car. In total was 5259 planes recorded.
<br>
<font size="3">4. <b>Flight Number:</b> One of the most important features. In total was 6965 flight numbers recorded for domestic flights.
<br>
<font size="3">5. <b>Origin Airport:</b> Airport of departure. Also very important feature. 333 Airports was recorded.
<br>
<font size="3">6. <b>State Origin:</b> State of departure. Important feature. I have this 3 top features which was in top 10 all my models I used in first part. 
<br>
<font size="3">7. <b>State Destination:</b> State of destination.
<br>
<font size="3">8. <b>Departure Time:</b> I split time of departure into 4 groups: night/morning/day/evening.
<br>
<font size="3">9. <b>Arrival Time:</b> I also split scheduled time of arrival into 4 groups: night/morning/day/evening.
<br>
<font size="3">10. <b>Length of Flight:</b> Scheduled length of flight time.
<br>
<font size="3">11. <b>Distance of the Flight:</b> Distance in miles between 2 points.
<p>
<font size="3"><u>First step with this predictors was:</u> I made categorical features from few of them e.g. flight number: I made 5 groups of flight number feature 1st was with 0-59 delays count, 2nd with 60-120 delays count and so on. Day of the week 7 categories.
<br>
<font size="3"><u>Second step was:</u> I converted all my categorical variables into Dummies. 
<br>
<font size="3"><u>Third step was:</u> I checked for Multicollinearity all my 602 features. Found 2 features which was highly correlated, and I decided to remove them.
<p>
<font size="3">To solve my classification problem I used 3 Models such as: LogisticRegression, DecisionTreeClassifier and RandomForestClassifire. Also I faced another problem as my data was high dimensional I couldn't use Models: SVM and KNN. Using PCA to reduce dimensionality from 600 to 400 and using models on reduced data I got a lower score. I think some important relations was broken after I used PCA, that why I decided to stick with my data without reducing dimensionality.
<p>
<font size="3">Before I talk about the results, I wanted to talk about my Regression and Multi Classification problems. I used same features but use them in a different way to create categorical variables. As I was focusing on length of delay I created categories based on length of delays for each group. e.g. flight number. I made 4 groups: 1st was with delays in interval 1-28 min, 2nd with 28-56 min and so on. Also there are was many very long delays on arrival, so I decided to keep delays only up to 120 min. Those long delays unpredictable and could be caused by bad weather condition, brakedown etc.
<p>
<b>Before</b>
<img src="/images/flightdelays/box1.jpg">
<p>
<b>After</b>
<img src="/images/flightdelays/box2.jpg">
<p>
<font size="4"><b><u>Results</u></b></font>
<p>
<font size="3"><u>Metrics and methods I used in this project was:</u> Accuracy, Logarithmic Loss, ROC AUC, Confusion Matrix, Features Importance.
<p>
<font size="4"><b>Classification problem</b>
<br>
<font size="3">In this part I built 3 working models. All of them gave me good result, but leader between all of them is my RandomForest, if we look at <b>Confusion Matrix</b> we can see that I got good score
<br>
<img src="/images/flightdelays/cm1.png">
<p>
Here we can see <b>ROC AUC</b> scores for all 3 models, RandomForest on a better shape 0.9831. 
<img src="/images/flightdelays/roc.png">
<p>
Also <b>Feature Importance</b> shows us most important ones for this model
<img src="/images/flightdelays/fi.png">
<p>
<font size="4"><b>Regression problem</b>
<br>
<font size="3">In this part as I mentioned before I used my variables in a different way rather than like in classification problem, I also create dummies from them. But the result was very poor, I tried LinearRegression, RidgeRegression, LassoRegression, ElasticNetRegression and RandomForestRegressor. All of them gave me <b>R^2 score: 0.10</b> which is very low. The main reason why I got this score because I used only this static features which is not enough for Regression problem. I could probably use variables such as: length of delay on departure, actual flight time. But I was focusing on static features only. At this stage I decided back to Classification problem and create few intervals of time which I managed to predict. 
<p>
<font size="4"><b>Multi Classification problem</b>
<br>
<font size="3">First attempt was I created 8 intervals and got score which wasn't too bad but still getting many wrong predicted results. Then I reduce number of intervals to 4: 
<p>
<img src="/images/flightdelays/int.jpg">
<p>
<font size="3">My goal was to get more right prediction results in length of delays which is more than 15 min because this information more important for the Air Traffic Controllers at the airport of destination.



<p>
<p>
<b>This blog still under construction. Thanks.</b>


