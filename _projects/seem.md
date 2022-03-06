---
layout: project
title: Similarity Evidence Explorer for Malware
subtitle: Interactive visualization for explaining malware clustering across multiple sets of attributes.
date: 2014-11-10
images:
  - seem.png
  - seem-histogram.png
  - seem-apt1-typos.png
---

 Similarity Evidence Explorer for Malware (SEEM) is a scalable visualization for comparing sets of attributes between malware samples. Malware analysts often need to understand if they are analyzing a novel malware sample or if it is a variant of an existing sample, and if it is a varient, in what ways is the sample different (e.g. did it add or remove functional components like a keylogger). This novel visual comparison tool allows malware analysts to do just that.

 Analysts select a malware sample the analyze, and SEEM loads it in the visualization along with all the other malware samples from the same cluster. Each category (e.g. system calls or imported DLLs) is a row. The left side of each row includes a histogram showing the degree of similarity with other malware samples in the cluster measured by Jaccard similarity. Using range sliders, users can filter out malware samples that are (dis)similar in the given category. The right side of each row is the list of other malware samples in the cluster ordered from most similar to least similar, and a miniature Venn diagram for each malware sample showing the amount of set overlap in this category. Users can expand a row to see a scrollable list of the elements within the category (e.g. the full list of DLLs imported by all malware samples in this cluster) and see which elements are present in which malware samples.

## Papers

Robert Gove, Joshua Saxe, Sigfried Gold, Alex Long and Giacomo Bergamo. "SEEM: A Scalable Visualization for Comparing Multiple Large Sets of Attributes for Malware Analysis." Visualization for Cyber Security 2014. \[[pdf](https://osf.io/eqtkd)\]