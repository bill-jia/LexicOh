# LexicOh!

##Introduction
LexicOh! is based on widely known utilities like Duolingo that aim to help the user to learn vocabulary in foireign languages. The essential difference is that our app accurately predicts what the user needs to learn according to what they currently know, as well as audio and visual input. Thanks to our word predictor, the voice speech recogniser and the image caption system* we are able to predict with a great degree of accuracy relevant unknown words for the user.

*The image recognition system is not fully implemented.

##Architecture

The architechture consists of separate backends and a single frontend (“the application”). One backend is in charge of the Big Data and Machine Learning recommendation system. The system develops a measure of relatedness between words by their co-occurrence in articles in a partial Wikipedia dump. It’s entirelly written from scratch in Python and receives data from a Flask-based REST API. The recommendations are sent back to the other backend, which is further described below.

The second backend ensures that everything is wired together and that both the frontend and the recommendation system receive consistent data. This backend is essentially a Node.js REST API supported by a Mongo database that saves some of the data sent by the user.

The frontend is an Android app written in Angular wrapped in Cordova.
