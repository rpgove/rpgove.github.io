---
layout: project
title: Rank-by-feature Exploration of Large Graphs
subtitle: O(v + e) feature extraction and rank-by-feature framework for interactively exploring subgraphs in large graphs.
date: 2019-05-18
images:
  - chiron-chi.png
  - gragnostics.png
---

In this project I developed a rank-by-feature framework for interactively exploring large graphs. My goal was to interrogate the idea that large graph visualizations are useless hairballs, and test whether we can usefully explore large graphs by ranking, filtering, and interacting with subgraphs.

My system, called Chiron, centered on a rank-by-feature framework: Chiron divided the graph into user-defined and community-based subraphs, which users can sort and filter using intelligible features to find subgraphs matching their desired characteristics, and then users can select subgraphs to interact with them and see them in the context of the full graph. The full graph overview is in the middle of the UI. To the left, analysts use the subgraphs panel to sort and select subgraphs, and open the settings panel. In the settings panel, users can filter by 10 graph features, hide or show automatically identified clusters of similar subgraphs (using *k*-means clustering with *k* that optimizes the silhouette score), or change the properties used to size and color the vertices and edges. When users select a subgraph, Chiron highlights it in the overview and displays it on the right where users can interact, see tooltips, and select vertices and edges to see their properties.

I developed solutions to several challenges in this project:

1. Slow rendering performance. SVG and canvas can be slow when rendering graphs with more than 1,000 vertices. WebGL is substantially faster at rendering, but it still requires transmitting all the coordinates and rendering attributes for each vertex to the front end, which can introduce latency. In my approach, I pre-rendered the overview visualization as a tile pyramid and used leaflet.js to pan and zoom in the front end. The x- and y-coordinates are known for each vertex, which allows for highlighting vertices. This provides fast interactivity and supports the necessary interactions, with the tradeoff of requiring rendering at data ingest time.
2. Slow extraction of understandable graph features. The subgraphs panel supports ranking and filtering subgraphs, but many featurization techniques pose problems: classic graph statistics are slower than O(v^2), but more modern techniques like graph kernels use features that are unintelligible to analysts. I developed a set of ten features that run in O(v + e) time by mixing some common fast features, finding fast alternatives for other features, renaming features to be more friendly to analysts, and inventing new features to measure important characteristics. I evaluated these features and found them to be both faster and better for modeling than graph kernels.

## Papers

Robert Gove. "Gragnostics: Fast, Interpretable Features for Comparing Graphs." Information Visualization 2019, **best paper award**. \[[pdf](https://osf.io/hrmq3/)\]