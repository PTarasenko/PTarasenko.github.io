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
<font size="3">My question was if I could use only static information that was given to Air Traffic Controllers before the flight to predict flight delays and their length on arrival. The data I was working with was taken from "Bureau of Transportation Statistic" for January 2018. And I was focusing only on Domestic Flight in USA.</font>
<p>
<p>
<b>On this graph I clearly can see how many delays and their length each Aircompany have</b>
<p>
<img src="/images/flightdelays/del1.png">
<p>
<p>
<b>Another very interesting thing that length of delays on departure longer than delays on arrival</b>
<p>
<img src="/images/flightdelays/del2.png">
<p>
<font size="3"><b>The features that I decided to focus for prediction flight delays are:</b>
<br>
<font size="3">1. <b>Day of the week:</b> Day of the flight departure (Mon - Sun)
<br>
<font size="3">2. <b>Airline Code:</b> Short name of Air Company. In total was <i>18 Air companies</i> recorded during that month.
<br>
<font size="3">3. <b>Tail Number:</b> It is like plate number on a car. In total was <i>5259 planes</i> recorded.
<br>
<font size="3">4. <b>Flight Number:</b> One of the most important features. In total was <i>6965 flight numbers</i> recorded for domestic flights.
<br>
<font size="3">5. <b>Origin Airport:</b> Airport from where plane will start his flight. Also very important feature.
<br>




# H1 Heading

## H2 Heading

### H3 Heading

Here's some basic text.

And here's some *italics*

Here's some **bold**

What about a [link](https://github.com/PTarasenko)?


Here's a bulleted list:
* First item
+ Second item
- Third item


Here's a number list:

1. first
2. second
3. third

Python code block:
'''python
     import numpy as np

     def test_function(x, y):
       z = np.sum(x,y)
       return z
'''

here's some inline code 'x+y'.

here's an image:
<img scr="123.jpg" alt="something cool">

Here's some math:

$$z=x+y$$

You can also put it inline $$z=x+y$$