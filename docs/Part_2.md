---
layout: default
title: Harmonisation Techniques 
nav_order: 3
---

# Harmonisation techniques
Here we apply harmonisation of acquisition and processes using:
1. simple Linear regression
2. The COMBAT technique to combine multi-site datasets of multiple individuals at different scanners. 

We demonstrate the advantage of COMBAT. 

The data we analyse include 624 images from 22 different acquisition sites, which include 7 different scanner models of 3 different manufactures and 2 magnetic fields (1.5T and 3T ).
The study comes from individuals either at-risk or affected by genetic frontotemporal dementia (FTD). The data features of the patients include Age, Estimated Year of symptom Onset (EYO), and Total Intracranial Volume (TIV).
We look at the difference (variability) in their mean other statistical measures and we compare them.

To access this leacture, click on the [harmonisation notebook link](https://mybinder.org/v2/gh/HealthBioscienceIDEAS/demon-imaging-harmonisation/HEAD?urlpath=lab/harmonisation.ipynb).

### Harmonisation with Linear Regression 

We Show some basic examples of LR from GENFI. First we add the site as a covariable and fit a LR then. Then we show differences in site between scanners with another LR fitting.

### Harmonisation with COMBAT

We do the same fitting to the site covariance as before using the neuroCombat for more precise harmonisation. We show advantages of COMBAT and why it would be useful, especially when numbers are small.


 







