---
layout: project
title: "Greadability.js: Graph Readability Library"
subtitle: "Greadability.js is a JavaScript library for calculating readability metrics on graph layouts."
date: 2018-06-30
images:
  - bestparameters.png
  - convergence.png
---

I developed an open source library to calculate graph layout quality metrics to help me evaluate graph layout algorithm research (see [d3-force-reuse](/projects/force-reuse) and [d3-force-sampled](/projects/force-sampled)). The metrics are useful for automatically estimating which layout is better, but I also showed a [proof of concept using them to automatically find higher quality layouts](https://bl.ocks.org/rpgove/553450ed8ef2a48acd4121a85653d880).

I included four global graph readability metrics, although it could be extended to include additional metrics:

* **Edge crossings measures** the fraction of edges that cross (intersect) out of an approximate maximum number that can cross.
* **Edge crossing angle** measures the mean deviation of edge crossing angles from the ideal edge crossing angle (70 degrees).
* **Angular resolution (minimum)** measures the mean deviation of adjacent incident edge angles from the ideal minimum angles (360 degrees divided by the degree of that node).
* **Angular resoluction (deviation)** measures the average deviation of angles between incident edges on each vertex.

## Live examples

* [Force Directed Layout Quality Convergence](https://bl.ocks.org/rpgove/8c8b08cc0ae1e1e969f5d2904a6a0e26)
* [Automatically Finding Better Force Directed Layout Parameters (10x10 Grid)](https://bl.ocks.org/rpgove/553450ed8ef2a48acd4121a85653d880)

## Code

[Greadability.js GitHub repo](https://github.com/rpgove/greadability)