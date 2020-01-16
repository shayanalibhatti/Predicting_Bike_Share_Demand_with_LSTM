# Predicting Bike Share Demand with LSTM

## Scope of Project:
The scope of this task is to observe different parameters such as season, hours, temperature, day of weeks etc., how they affect the hourly bike share demand explained by “cnt” column in Capital Bike Share dataset that can be found at https://archive.ics.uci.edu/ml/datasets/bike+sharing+dataset.

![image](https://user-images.githubusercontent.com/41015749/72564567-0b9b8e00-387e-11ea-9095-598cc8dc11fc.png)

## Methodology:
First, I visualized the dataset in Tableau to see how Bike Share Demand count “cnt” is varying with respect to hours of the day. My focus was to see how weekend “cnt” varies from weekday’s “cnt” and it was observed that weekday “cnt” displays a “bat ear” kind of response meaning that “cnt” was highest from 6am to 10am and from 4pm to 7pm with a little surge on noon (probably for lunch time) which makes sense as these times are for going to and leaving from office/schools/college etc. An example of bike share hourly data for 7th-11th Feb, 2011 is shown in figure below:

![weekday_pic](https://user-images.githubusercontent.com/41015749/72563506-d42be200-387b-11ea-9f7a-ba532f5e478d.jpg)

Whereas on Saturdays and Sundays a “mountain-like” shape is observed meaning that “cnt” would increase from 6am to 2pm and then decrease after 3pm most of the times. An example of this effect is shown in figure below for 12th and 13th February, 2011 (Saturday, Sunday) bike share data.

![weekend_pic](https://user-images.githubusercontent.com/41015749/72563562-eb6acf80-387b-11ea-9d96-fdbc48a887cf.jpg)

## Observations:

Following are the observations:

1) Figure 1.3 shows that most of the "cnt" values fall between 40 to 280 however there are a lot of outliers too.

![cnt_pic](https://user-images.githubusercontent.com/41015749/72564323-78faef00-387d-11ea-8ca4-48449985477c.jpg)

2) Figure 1.4 shows that January had least amount of bike share whereas in summer season bike share was high.

![cnt_months_pic](https://user-images.githubusercontent.com/41015749/72565102-29b5be00-387f-11ea-8e97-1bb52e22f719.jpg)

3) Figure 1.5 shows that when weather was clear bike share was maximum, when misty, it was less, when light snow it was lesser and when heavy rain, it was least.

![cnt_weather_pic](https://user-images.githubusercontent.com/41015749/72564059-f5d99900-387c-11ea-9b61-bc7423dee720.jpg)

4) Figure 1.6 shows that on weekends, bike share was less compared to weekdays.

![cnt_working_day_pic](https://user-images.githubusercontent.com/41015749/72565258-76999480-387f-11ea-8596-bba02f062b2b.jpg)

5) Figure 1.7 shows that bike share is high from 7 to 9 am then from 4 to 8pm which makes sense as 7 to 9am and 4 to 8pm are school/office going and leaving time respectively.

![cnt_hours_pic](https://user-images.githubusercontent.com/41015749/72564149-26213780-387d-11ea-8c4d-ec3746d2d817.jpg)

6) Figure 1.8 shows that the higher the temperature, the higher the bike share. Colder temperatures mean less bike share.

![cnt_temperature_pic](https://user-images.githubusercontent.com/41015749/72564171-333e2680-387d-11ea-9f2e-82b3212fb1c6.jpg)

## Model Selection:

There are a lot of machine learning models used for predicting time-series data such as random forests, gradient boosted trees, LSTMs,  etc. Since, tree based models suffer a lot from overfitting and I had prior knowledge of LSTMs, therefore, I decided to use LSTMs, since they are known to work well for capturing the trends in sequences. I used keras library and python language for my work.

![image](https://user-images.githubusercontent.com/41015749/72564443-bc555d80-387d-11ea-9fb5-cf1d46019acb.png)

## Result:

LSTM based model’s mean absolute deviation was 144.76 compared to actual data which had 149.7. Figure 1.9 shows the comparison of actual data vs LSTM predicted data. LSTM based predictor model is found to be working well.

![cnt_comparison_pic](https://user-images.githubusercontent.com/41015749/72564490-d4c57800-387d-11ea-8f64-95339a7bfcfe.jpg)

