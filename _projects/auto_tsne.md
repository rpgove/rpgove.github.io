---
layout: project
title: t-SNE Guidance and Automation
subtitle: New guidance for using t-SNE, and a new method to automatically optimize visualizations.
date: 2022-03-23
images:
  - scatterplot-matrix.png
  - tsne-plots.png
  - mean-accuracy-metric.png
---

How can we more effectively use t-SNE to visualize high-dimensional data? And can we _automatically find optimal t-SNE parameters for your data?_

We revisit prior guidelines by conducting a study of t-SNE on 691 data sets, finding that many prior parameter range recommendations are unhelpful. From our study we recommend:

- Use perplexity=16, learning rate=10, exaggeration=1 as a starting point for good visualizations
- When trying other values, use perplexity in 2-16, learning rate in 10-640, and exaggeration in 1-8

We also developed Auto t-SNE to automatically find good t-SNE parameters! It uses a neural network to predict t-SNE accuracy given a data set and parameter combo. Picking the best parameters takes about one second, way faster than a brute force approach! When evaluating Auto t-SNE we found it performed comparably to the OpenTSNE defaults, and dramatically better than the sklearn defaults.

We also replicated work by Belkina _et al._ (2019) and Kobak & Berens (2019):

- Learning rate = n/12 is good practice and generalizes from large omics data to smaller tabular data.
- Perplexity = n/100 does not appear to generalize from large omics data to smaller tabular data.

## Blogs

[New Guidance for Using t-SNE](https://twosixtech.com/new-guidance-for-using-t-sne/)

## Papers

Robert Gove, Lucas Cadalzo, Nicholas Leiby, Jedediah M. Singer, Alexander Zaitzeff. "New Guidance for Using t-SNE: Alternative Defaults, Hyperparameter Selection Automation, and Comparative Evaluation." Journal of Visual Informatics (proc. Visualization Meets AI 2022). \[[pdf](https://osf.io/6t5ax/)\]