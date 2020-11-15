---
layout: single
title:  "MN Bus Locator"
excerpt: "MetroTransit bus information app made for the frequent rider"
date:   2020-05-16 00:00:00 -0500
search: true
comments: true
header:
  teaser: /assets/images/mn-bus-locator/mn-bus-locator-arch.png
categories:
  - projects
tags:
  - MN Bus Locator
  - React
toc: true
toc_sticky: true
---

# Background

So I live in Minnesota and in 2019 we had a [terrible, terrible snow storm](https://www.weather.gov/mpx/snowymonth){:target="_blank"} earlier in the year. 

The snowstorm was huge for me because I take the bus everyday for my commute to work and it weaked havok on the reliability of the local bus 
schedules and stops. Busses were late to stops or didn't even show up because of a temporary re-route. There's a few resources provided by my local transit authority but they were either old and hard to use or just unstable. At a stop and text the stop number to the automated phone number? Many times no response back. Want to see rider alerts? Going to the transit site and searching a route doesn't have the alerts there. They're on a different site. Want to see where the busses actually are? It's a separate section of the site (nested deeply) that is unresponsive and clunky.

(I should be fair, at the time of writing this I relooked at their website and saw that they resolved a lot of my pain points above).
{: .notice}

I had all these problems during the snowstorm so in response I made [MN Bus Locator](https://mn-bus-locator.web.app){:target="_blank"} to try and present the bus information in a more streamlined way for the frequent rider like me.

# Site Goals

The thing I wanted to do when visiting my transit authoriy site was search a route and get all info related to the route. On my site I have the route search bar look up associated information like bus locations, route stop departures, and rider alerts. Search a route and one can see the information more clearly and only a click or two away. A stop id (the thing you text I was talking about earlier) can also be searched to pull up the busses that are en route to the searched stop.

And learning some new things too.

## Features Lacking

There are a few things that are clearly lacking though:
  - What path the bus takes from stop to stop
  - We've got busses on the map for departures at a stop but no info for it on the departures page.
  - Multi value search

# How it Works

Here's the structure of Mn Bus Locator:

![MN Bus Locator Architecture](/assets/images/mn-bus-locator/mn-bus-locator-arch.png "MN Bus Locator Architecture")

## Postgres Database

Pretty standard in terms of storage here. I keep data like route or stop information here.

## Raspberry Pi

Runs scheduled jobs using cron It does 2 main things:

1. Wake up the application early in the morning
2. Download the newest version open sourced metro transit information then resync the database with new info

## Metro Transit API

Source of truth for lots of data like bus locations or routes currently in service.

## MN Bus Locator API

This is an api that glues the other services in the application together. It does a few things:

1. Programmatic connection to the database to serve stored route and stop information.
2. Connector to the Metro Transit api to get real time data.
3. Caching. Want to reduce doing the same thing many times and reduce the number of requests to the metro transit api.
4. Transform data such as creating geojson based on busses.
5. Handles emailing when a user fills out the contact form.
6. Some scheduled jobs

Here are some of the languages and libraries it uses:

- Kotlin and Java (mainly from generated files)
- Spring Boot
- Flyway
- Jooq
- Retrofit2
- Micrometer
- Springfox
- Spock
- Docker
- Deployed on Heroku


## MN Bus Locator Website

Here is the window a user sees into the application and how they'll get information.