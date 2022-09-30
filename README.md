# Ridesharing-Company---Ola-Bike-Rides-Request-Demand-Forecast
Data File Link: https://drive.google.com/file/d/17Wkljr22Su5zYd8CDmYcCaE0OjZtRxC-/view?usp=sharing


Business Problem

Ola Bikes are suffering losses and losing out from their competition due to their
inability to fulfill the ride requests of many users. To tackle this problem you are
asked to predict demand for rides in a certain region and a given future time window.
This would help them allocate drivers more intelligently to meet the ride requests
from users.

Goal

You have to predict ride requests (demand forecast) for a particular latitude
and longitude for a requested future time window/duration.

Data Description

Raw Data contains a `number` (unique for every user), ride request DateTime (IST
time),
pickup and drop location latitude, and longitude.

Data Fields

1. number: unique id for every user
2. ts: DateTime of booking ride (IST time)
3. pick_lat: ride request pickup latitude
4. pick_lng: ride request pickup longitude
5. drop_lat: ride request drop latitude
6. drop_lng: ride request drop longitude

Defining a Good Ride Request

Ola Management knows the task is not easy and very important for their business to
grow.
Hence, their business team has provided you some guidelines to follow.
1. Count only 1 ride request by a user, if there are multiple bookings from the
same latitude and longitude within 1hour of the last booking time.
2. If there are ride requests within 8mins of the last booking time consider only 1
ride
request from a user (latitude and longitude may or may not be the same).
3. If the geodesic distance from pickup and drop point is less than 50meters
consider that ride request as a fraud ride request.
4. Consider all ride requests where pick up or drop location is outside India
bounding box: ['6.2325274', '35.6745457', '68.1113787', '97.395561'] as
system error.
5. Karnataka is our prime city where we have a lot of drivers and ride requests to
fulfill. We would not love to serve rides that are outside Karnataka and have
pickup and drop geodesic distance > 500kms. Karnataka bounding box:
['11.5945587', '18.4767308','74.0543908', '78.588083']

Predict Task to test your model

After model development, Ola has requested us to build a prediction pipeline for the
deployment of the model. To test our prediction pipeline they have provided us clean
data (
filtered rides requests data based on good ride definition conditions ) of 2021-03-26
based
on which they have requested us to predict/show initial hours rides request demand
forecast for 2021-03-27.
