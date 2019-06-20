---
title: "Controllable Car in AR"
excerpt: "App I made in Unity using Google's ARCore that allows me to control a car using on screen joysticks."
categories:
  - projects
tags:
  - ARCore
  - Unity
date: 2018-10-23 20:15:48 -0500
repository: scott-mcnulty/ar-experimentation
# toc: true
comments: true
header:
#   image: /assets/images/unsplash-gallery-image-1.jpg
  teaser: assets/images/controllable-car/version-0.gif
# sidebar:
#   - title: "Role"
#     image: http://placehold.it/350x250
#     image_alt: "logo"
#     text: "Designer, Front-End Developer"
#   - title: "Responsibilities"
#     text: "Reuters try PR stupid commenters should isn't a business model"
# gallery:
#   - url: /assets/images/unsplash-gallery-image-1.jpg
#     image_path: assets/images/unsplash-gallery-image-1-th.jpg
#     alt: "placeholder image 1"
#   - url: /assets/images/unsplash-gallery-image-2.jpg
#     image_path: assets/images/unsplash-gallery-image-2-th.jpg
#     alt: "placeholder image 2"
#   - url: /assets/images/unsplash-gallery-image-3.jpg
#     image_path: assets/images/unsplash-gallery-image-3-th.jpg
#     alt: "placeholder image 3"
---

## Overview

I was curious about Augmented Reality so I decided to try to make this project using Unity and Google's ARCore. The app allows me to use my phone to control a small car on detected planes.

## Demo

![v0 Demo](/assets/images/controllable-car/version-0.gif)

## Main Features

- Look and move around to detect planes.
- Tap a plane to spawn a car.
- Use the menu to change the scene state into one of two states:
    - Edit: To be able to spawn cars.
    - Nonedit: Car does not spawn when tapping a plane.
- Jump button currently disabled.
- No vehicle options at the moment.
- Left joystick controls forward and backward movement while right joystick is to turn.


### Link to code

[ar-experimentation](https://github.com/scott-mcnulty/ar-experimentation){:target="_blank"}