---
layout: project
title: Periodic Traffic Visual Analysis
subtitle: A threat hunting tool for identifying malicious network traffic via periodic signals.
date: 2018-10-22
images:
  - increasing-periodicity-subset.png
  - periodic-traffic-diagram.png
---

Indentifying network traffic from malware is important but challenging to differentiate from allowed network traffic. Malware tends to generate periodic network traffic to command and control servers, so one strategy is to look for periodic signals in network logs. I worked with a data scientist who applied Fourier transforms to this problem, and we collaborated on a visualization to show the results to cyber threat hunting teams. We developed a visualization that displayed turned the algorithm results into consummable visualizations, and interestingly we found that the [Visual Information Seeking Mantra](https://ieeexplore.ieee.org/document/545307) (overview first, then zoom and filter, then details on demand) was less useful than a sortable table to direct analysts to the most salient results.

## Videos

[Demo video](https://www.youtube.com/watch?v=Oisi6PlepTA)

## Blogs

[Visualizing Automatically Detected Periodic Network Activity](https://twosixtech.com/visualizing-automatically-detected-periodic-network-activity/)

## Papers

Robert Gove and Lauren Deason. "Visualizing Automatically Detected Periodic Network Activity." Visualization for Cyber Security 2018. \[[pdf](https://osf.io/xpwfe/)\]