---
layout: project
title: O(n) Random Sampling Graph Layouts
subtitle: d3-force-sampled is a D3.js module that drastically speeds up graph layouts by using random sampling.
date: 2019-05-20
images:
  - dwt.png
  - speed-comparison.png
  - eurovis2019.png
---

Using random sampling I developed [d3-force-sampled](https://github.com/twosixlabs/d3-force-sampled), a [D3.js](https://d3js.org) module, to compute force-directed graph layouts about three times faster than the standard algorithm. The standard algorithm runs in O(n log(n)) time and space, whereas my algorithm is O(n) time and space. The difference is that the standard algorithm uses the [Barnes-Hut approximation](https://jheer.github.io/barnes-hut/) to calculate very accurate forces, but this generates a spacial tree in O(n log(n)) time that occupies O(n log(n)) space every iteration. In contrast, my algorithm approximates forces by sampling n^(3/4) vertices to update at an iteration and then sampling n^(1/4) vertices to use for calculating Coulombic forces. The algorithm works surprisingly well, although the layouts can look more random and less symmetric. Running ten iterations of the Barnes-Hut algorithm afterwards is enough to resolve the low-level randomness, and it is nearly as fast as the pure random sampling algorithm.

I attempted to use a similar approach to speed up spring force calculation, but the results were not satisfying. I reduced the overall runtime for all iterations from O(i * e) to O(e). But this only translated to at most a 10% runtime improvement in practice, and it came at the cost of substantially reducing the layout quality.

## Live examples

* [EuroVis 2019 Twitter interaction network](https://bl.ocks.org/rpgove/e66f1d921718813ecf507178c7dc8d12)
* [Composing multiple forces and constraints with Random Vertex Sampling](https://bl.ocks.org/rpgove/2c523eb97f594de8ae0d04e305495c72)
* [Random Vertex Sampling vs. Barnes-Hut Approximation](https://bl.ocks.org/rpgove/28345b65a65753ecbabc3acbe30c3d70)
* [Linear-time force-directed graph layouts with random vertex sampling](https://bl.ocks.org/rpgove/14bf7407d66cd364ce399ea0540e67b9)

## Blogs

[Graph Layout by Random Vertex Sampling](https://twosixtech.com/graph-layout-by-random-vertex-sampling/)

## Code

* [d3-force-sampled GitHub repo](https://github.com/twosixlabs/d3-force-sampled)
* [Vertex sampling experiment and analysis](https://osf.io/nb7m8/)
* [Edge sampling experiment and analysis](https://osf.io/4ja29/)

## Papers

Robert Gove. "A Random Sampling O(n) Force-calculation Algorithm for Graph Layouts." Computer Graphics Forum 2019 (proc. EuroVis). \[[pdf](https://osf.io/2vpe4/)\] \[[osf](https://osf.io/nb7m8/)\]

Robert Gove. "Force-Directed Graph Layouts by Edge Sampling." Large Data Analytics and Visualization 2019. \[[pdf](https://osf.io/6q7ck/)\] \[[osf](https://osf.io/4ja29/)\]