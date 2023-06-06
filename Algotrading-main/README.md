# Algotrading
This is a support-vector machine based algotrading model which trains on a OHLCV dataset.

**3 Month SVC Classifier**

Initially, I trained the support vector machine on the 3 month period from April 2nd 2015 to July 2nd 2015. 
The decisions predicted from the classifier trained on this historical 3 month window were used to obtain predicted returns, which were then graphed alongside actual returns.

![svc_3-month](https://user-images.githubusercontent.com/54637095/226731265-c8059aed-2402-4a7a-92e2-9e84faa7d235.png)


**1 Month SVC Classifier**!

![svc_1-month](https://user-images.githubusercontent.com/54637095/226736032-5e6de8da-1ae7-420c-966d-1580cb7ab62f.png)

Reducing the historical training window from 3 months to a single month (April 2nd 2015 - May 2nd 2015) surprisngly doesn't affect our predictions too noticeably. There are few slight differences that are extremely subtle but probably not easy to pick up on at first glance.

**15 day SVC Classifier**!

![svc_15-day](https://user-images.githubusercontent.com/54637095/226741153-5d0d6825-72fc-4bc8-aa85-442b7897f6e6.png)


Interestingly, as we reduce the window even more, the area of the timeframe that sees differences between actual and predicted returns is sequestered more tho the right.


**6 Month SVC Classifier**

![svc_6month](https://user-images.githubusercontent.com/54637095/227732568-ea8fcbdb-4f51-41ee-9b92-9aac9124f69f.png)

By increasing the window, we see that the actual and predicted returns begin to diverge earlier. There's also in general more of a difference between the two quantities and it appears that the predicted returns at the 6 month window is actually worse for the most part than what is observed with the 3 month window

**6 Month Adaboost Classifier**

![adaboost_6-month](https://user-images.githubusercontent.com/54637095/227734223-f48d9ab3-1208-4376-a101-d54cc89781aa.png)


Utilizing Adaboost, an ensemble decision tree method, as our underlying ML architecture for prediction drastically increases performance for the 6 month window.

**3 Month Adaboost Classifier**


![adaboost_3-month](https://user-images.githubusercontent.com/54637095/227734461-f362bef9-70c5-48c8-acb3-d0efb97e53e0.png)


Interestingly, even though the svc 3 month model produced seemingly stronger results for the majority of the timeframe than what was observed in the 6 month svc model, the 6 month adaboost classifier was more consistently stronger in predicted returns than the 3 month adaboost classifier. This suggests that if a certain window is optimal for one one classifier, that window won't necessarily be optimal for another classifier. This necessitates the need for a hyperparameter grid search where each possible model and each possible hyperparameter is tried out.
