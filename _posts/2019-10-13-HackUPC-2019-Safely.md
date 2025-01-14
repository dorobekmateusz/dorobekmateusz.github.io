---
title: "Safely - The Intelligent Travel Assistant"
date: 2019-10-13
permalink: /posts/2019/10/HackUPC-2019-Safely
excerpt: 'I’ve won Hack UPC “Use of AI in real-life cases” challenge. My team created a web app that makes your travel safer using ML model predicting severity of accidents.'
tags:

  - HackUPC
  - Safely
  - Classification
---
<iframe width="420" height="285" src="https://www.youtube.com/embed/xaulZbueQoc?autoplay=1"></iframe>
Our submission on [Devpost](https://devpost.com/software/safely-sa5lte) and [ML](https://mateuszdorobek.pl/posts/2019/10/McKinsey-Hack-The-Crash) report

## Inspiration

Nowadays people travel without awareness. We would like to make travels safer, using Big Data and AI.

## What it does

Our model predicts the severity of accidents. We also created a web app that suggests useful tips to make your travel safer.

## How we built it

We used many advance ML techniques and frameworks to process data and perform classification using Python language and the libraries written in it. We built an app using modern and fast searching engines as Algolia and Open Street Maps API. We have also implemented a simple and accessible UI design with Angular and Google Maps API.

## Challenges we ran into.

- We have a lot of problems with the dimension reduction of the dataset.
- Setting a parameter space for GridSearch was also a big challenge.
- Feature processing and training were very time-consuming.
- We had to solve problem with Open Street Routing Machine - the demo which allows finding the route between two points has limits, so we have deployed the webservice on the AWS virtual machine.
- The use of APIs was difficult because some of them have documentation which is hard to understand and our goal was tougher to achieve.
- The way to display complex results in an accessible way for everyone was also a brainstorming challenge.

## Accomplishments that we're proud of

- Creating an ML application capable to achieve such a good score in the classification task.
- Creating a Web App that uses the predictions to help people to travel safer.
- The method to transform from points to routes and the way we implemented the accident geo search.
- We created a cool group of friends and meet a lot of interesting people during HackUPC 2019.

## What we learned

- Try to use PCA and other dimension reducing techniques as LDA or QDA instead of feature selection.
- Know your algorithm parameters to properly GridSearch over them.
- Feature processing may be very time-consuming use functions and generalize your tasks.
- Consuming API using Angular and interact with different APIs at the same time.
- Simple and useful UI project designing.
- Sleep at least 4 hours a day to be more productive.
- How to configure CodeBuild and CodePipeline in AWS Platform.

## What's next for Safely

We will expand it to other countries, we will also add other sources of data and the newest technology to make your travel even safer.

## Built With

- [algolia](https://devpost.com/software/built-with/algolia)
- [amazon-web-services](https://devpost.com/software/built-with/amazon-web-services)
- [angular.js](https://devpost.com/software/built-with/angular-js)
- [bootstrap](https://devpost.com/software/built-with/bootstrap)
- [docker](https://devpost.com/software/built-with/docker)
- [flask](https://devpost.com/software/built-with/flask)
- [git](https://devpost.com/software/built-with/git)
- [google-maps](https://devpost.com/software/built-with/google-maps)
- [openstreetmap](https://devpost.com/software/built-with/openstreetmap)
- [python](https://devpost.com/software/built-with/python)
- [scikit-learn](https://devpost.com/software/built-with/scikit-learn)
- [typescript](https://devpost.com/software/built-with/typescript)

Check out [GitHub Repo](https://github.com/Safe-ly/) and [HackUPC 2019](https://hackupc2019.devpost.com/)

![HackUPC-279](https://github.com/mateuszdorobek/dorobekmateusz.github.io/blob/master/files/photos-hackupc/HackUPC-279.jpg?raw=true)

![HackUPC-1210](https://github.com/mateuszdorobek/dorobekmateusz.github.io/blob/master/files/photos-hackupc/HackUPC-1210.jpg?raw=true)

![HackUPC-1229](https://github.com/mateuszdorobek/dorobekmateusz.github.io/blob/master/files/photos-hackupc/HackUPC-1229.jpg?raw=true)

Photos Team Hack UPC

13 Oct 2019 [Mateusz Dorobek](https://mateuszdorobek.pl/) 
