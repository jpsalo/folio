---
title: HN Viz
subtitle: _"Good Stories"_
summary: Discovering interesting stories from Hacker News
date: "2019-05-08T00:00:00Z"
share: false
profile: false
type: project

# Optional external URL for project (replaces project detail page).
external_link:

image:
  preview_only: true
  focal_point: Smart

---

![Bubble chart](/img/hn-viz-1.png)

HN Viz is an interactive data visualization application with Hacker News data for discovering interesting stories. The app shows 100 most voted and 100 most commented stories per each year in a bubble chart. Stories are divided into four category types: stories, jobs, projects and questions, and the bubble size is based on how many days was the discussion active. Contextual views show monthly statistics in bar charts, and also metadata of selected story with a link to the original thread on Hacker News. Application is [here](http://hn-viz.herokuapp.com/)

{{< figure src="/img/hn-viz-2.png" caption="How well did the story perform that month?" >}}

# Problem

Is a story worth reading? What could explain votes and comments and duration of discussion? Is a story with a lot of votes a "news" item and story with lot of comments a "discussion"? This project aimed to answer aforementioned questions throughout the process and, once the domain and technologies became more familiar, the unifying objective for the project became: _"What does the data show about good stories?"_ (Fisher & Meyer, 2018, p. 34). As the objective suggests, knowledge discovery emerged as the main purpose of the visualization.

# Design rationale
The ideation and design drafts were done with lo-fi paper prototyping and while the method was not perfect, it was sufficient for this project. A relatively good tool for prototyping was found by stumbling upon Google Data Studio, a tool which allows exploration of the intermediate BigQuery jobs.

In regards of scatter plots, Fisher writes in Making Data Visual (Fisher & Meyer, 2018, p. 77): _"At a large number of points, a scatterplot can become a black blob"_, and the solution can be a bit overwhelming at first, which is against the information seeking mantra: _"Overview first, zoom and filter, details on demand"_ (Shneiderman, 1996), so some planning was required to improve encoding of the data in order to avoid occlusion and it was alleviated by keeping the amount of stories per year in a reasonable small number. Area, hue, density and position are the visual encoding variables used in bubble chart. A future improvement could be to further split items with a type "story" by, for example, domain or meta stories (stories about Hacker News) etc. so the amount of stories could be increased.

How to gain an overview of the entire collection? What is application’s _"null island"_? These were some of the questions asked when the visualization was made fundamentally interactive by adding the contextual view. It turns out that, on average, author has only one "good" story so, instead of discovering information about the author, the implementation shows—by clicking a story—statistics from the month the story was posted in two separate bar charts, one with the number of votes and the other with the number of comments as y-axis, in descending order. Rationale for these views is to enable to see what other stories gained traction around the same time, i.e. details on demand. The addition of navigation between focused and contextual view in the form of monthly statistics bar chart brought the biggest challenge of the project: brushing and linking and interacting with multiple linked views.

The newly introduced detail view also required to take a step back and do some data cleaning, and raised the need to make a design decision on how to make interesting stories more visible, by taking into account the available data and feasibility of implementation. The bubble size—or, magnitude estimation—has couple things to consider, especially optimization of marker size by normalizing the duration based on the descendants of the story. Plotly Dash has an algorithm which helps with the scaling, and rest was achieved with simple arithmetics and a logarithmic scale to make stories with long discussion and less comments relatively more visible than the somewhat obviously interesting stories (i.e. lot of comments or votes). The implementation does a decent job in answering the question of _"What does the data show about good stories?"_
