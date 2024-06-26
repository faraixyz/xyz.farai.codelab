---
title: "Math.floor(it): Now You Can See if Speeding Is Worth It"
date: 2017-01-20
lastmod: 2019-10-28
description: Going into detail about the project I made at Uncommon Hacks 2017.
projects: [math-floor-it]
draft: false
---

![](/images/math-floor-it.png)

[DevPost](https://devpost.com/software/math-floor-it) | [Code Repository](https://github.com/faraixyz/math-floor-it) | [Try It](https://faraixyz.github.io/math-floor-it/)

During [Uncommon Hacks](/content/notes/uncommon-hacks-2017.md), I worked with 3 other students on Math.floor(it). Math.floor(it) is a rather silly web app designed to calculate the cost of speeding as well as its benefits. The idea came about when one of the team members wondered how much faster his 1-hour commute would be if he ignored all the traffic lights and drove 25 miles over the speed limit.

The app would work by taking in two addresses in Chicago where after pressing on the cute little car, it would plot a route between the two points, point out all the speed cameras and red light cameras along the way and give you information on time savings, fines and your probability of dying.

Our stack was pretty straight basic. We set up a static web page using HTML, JavaScript, jQuery, SaaS as a CSS preprocessor and SVG’s for our animations, like the cool car that drives in. The data on the camera locations were sourced from the [City of Chicago’s Data Portal](https://data.cityofchicago.org/) which was then downloaded as JSON in order to use it in our app. For the mapping, we used the [Google Maps JavaScript API](https://developers.google.com/maps/documentation/javascript/) and built a lot of functionality around it.

While making Math.floor(it), we faced a couple of challenges. Firstly, we discovered that the `isLocationOnEdge()` function was unreliable since it would sometimes show up on paths where there was no camera touching the path as well as ignoring cameras on the path. `checkBounds()` was a possible alternative, but given our time constraints, we choose to stay with `isLocationOnEdge()`. Another problem had to do with understanding the asynchronous nature of JavaScript when using `$.getJSON()` to get the camera data.

In the future, we hope to refactor our code, add more cities, solve the `isLocationOnEdge` inconsistencies and make further polished to the UI. We might also factor in additional data to improve the app's accuracy since it’s unlikely that someone would drive 25 MPH over the speed limit without either a cop noticing or hitting traffic, less so in Chicago.

In all, our efforts won us two prizes; best beginner hack since this was there the first hackathon for one over of the team members as well as Most Uncommon for symbolizing the hackathon which was rather eccentric. After all, the prize was a Muppet plant. Given how we didn’t know each over before the even, we knocked up something pretty decent within a weekend.
