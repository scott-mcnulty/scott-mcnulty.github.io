---
layout: single
title:  "Selenium Internet Checker"
excerpt: "A python script using Selenium to check if my internet is still up"
date:   2019-03-13 20:15:48 -0500
search: true
header:
  teaser: /assets/images/internet-checker/internet-checker.gif
categories:
  - projects
tags:
  - Python
  - Selenium
---

The modem at my parent's house wasn't very good because it dropped the internet connection every few hours. Usually I'd walk downstairs to restart it but after a few weeks of that I got fed up with it so I made this script to check the modem's status. If the modem is connected to the internet, great! Otherwise if it's not connected then the script restarts the modem in an attempt to reconnect it.

Here's a demo:

![demo of internet checker](/assets/images/internet-checker/internet-checker.gif)

### Link to code

[internet-checker](https://github.com/scott-mcnulty/internet-checker){:target="_blank"}