---
layout: project
title: GitHub Dashboard for Analyzing Repo Health and Suitability
date: 2020-01-30
images:
  - singlebig-no-annotation.png
  - multi-no-annotation.png
---

Software engineers regularly encounter problems when choosing an open source library to use for their projects: which libraries represent risks because of their activity levels or underlying technologies? We had multiple conversations with software engineers to fully flesh out concerns that we could address. Then we developed a Chrome plugin to insert a dashboard into GitHub repository homepages to show useful information about the repository's technologies and activity. This includes a breakdown of the main technologies detected in the repository, commits over time, a burndown chart, and a bus factor chart. We also developed a seperate tool to compare multiple repositories, such as different Python machine learning libraries. We found these prototypes to be very useful, and we believe users would benefit from incorporating this type of information directly into code repository homepages.

## Blogs

[Choosing Open Source Libraries and Analyzing Risks](https://twosixtech.com/choosing-open-source-libraries-and-analyzing-risks/)

## Papers

Casey Haber and Robert Gove. "A Visualization Tool for Analyzing the Suitability of Software Libraries via Their Code Repositories." Visualization and Data Analysis 2020, **best paper award**. \[[pdf](https://osf.io/j28ev/)\]