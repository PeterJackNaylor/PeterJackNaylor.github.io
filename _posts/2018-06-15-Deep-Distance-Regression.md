---
layout: post
title: 'Deep Distance Regression'
tags: [Publications]
---

## Paper
The Paper 'Segmentation of Nuclei in Histopathology Images by deep regression of the distance map' by *Peter Naylor, Thomas Walter, Fabien Reyal and Marick Laé* has been submitted to TMI.

## Data freely available
The data made freely public as mentionned in the paper can be found [here](https://zenodo.org/record/1175282#.WyP61xy-l5E). 
The code can be found [here]( https://github.com/PeterJackNaylor/DRFNS).
The results involving the comparaison of the different methods can be found [here](https://cloud.mines-paristech.fr/index.php/s/OxbkrVqkvtFGDyR).

## Summary of the paper
We focus ourself on the problem of touching nuclei in histopathology images, i.e. instance segmentation applied to nuclei. We transform the standard classification problem by a regression problem and a post-processing scheme. Instead of predicting categorial variable we try to infer the distance between a given pixel and it's distance to the border, see figure TODO. The post-processing goes as follows, we join two maximum a posteriori of the distance map if and only if we can find a path that does not decrease of a certain size between them. This type of post-processing is ideally suited for the previous task. We believe that formulate the problem into a distance regression problem helps the model learn the concept of a cell better. Indead, the main difference with the standard classification arises in areas where the model is uncertain and will try to maximise per pixel probabilities. This situation does not arise with the distance regression and there for creates nice and smooth segmentation results as one can see in figure TODO