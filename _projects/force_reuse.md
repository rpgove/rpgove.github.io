---
layout: project
title: Faster Graph Layouts by Reusing Force Approximations
subtitle: The d3-force-reuse D3.js module speeds up D3's graph layout algorithm by reusing the Barnes-Hut approximation.
date: 2018-11-18
images:
  - speed-comparison.png
  - les-miserables.png
---

I ran several experiments to test speeding up force-directed layout algorithms by reusing force approximations. Force-directed layout algorithms run iteratively, and commonly they use a Coulombic force approximation, such as Barnes-Hut, to run faster. However, vertex positions tend to change slowly, so it's probable that reusing approximations might speed up layout algorithms at the cost layout quality. I tested this hypothesis using both Barnes-Hut and fast multiple approximation methods. I found that reusing the approximation and calculating a new one every 13 iterations reduces runtime by 9% to 18% without decreasing layout quality when using the Barnes-Hut approximation. This led me to develop the [d3-force-reuse speed comparison](https://bl.ocks.org/rpgove/ecee35052e3e81126dcefff134c06dae) module for [D3.js](https://d3js.org). I published a [research paper](https://osf.io/wgzn5/) that discusses the experiments in more detail.

## Live examples

* [d3-force-reuse speed comparison](https://bl.ocks.org/rpgove/ecee35052e3e81126dcefff134c06dae)
* [Faster Force-Directed Graphs with d3-force-reuse](https://bl.ocks.org/rpgove/98820c49a3d7fd0d4d628402536aa60b)

## Blogs

[Faster force-directed graph layouts by reusing force approximations](https://twosixtech.com/faster-force-directed-graph-layouts-by-reusing-force-approximations/)

## Code

* [d3-force-reuse GitHub repo](https://github.com/twosixlabs/d3-force-reuse)
* [Open date for the experiments and analysis](https://osf.io/re7nx/)

## Papers

Robert Gove. "It Pays to Be Lazy: Reusing Force Approximations to Compute Better Graph Layouts." Forum Media Technology 2018, **best paper award**. \[[pdf](https://osf.io/wgzn5/)\] \[[osf](https://osf.io/re7nx/)\]