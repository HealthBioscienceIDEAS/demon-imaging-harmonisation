---
layout: default
title: Harmonisation Techniques 
nav_order: 3
---
## 1st part : Differences in image acquisition
This part of the lecture shows why images are different. Even the scans of the same individual show differences in physiological noise, instrument noise, differences in hardware and software. The gold standard of identifying these differences is often a “travelling head” study, where a small handful of individuals are scanned at multiple sites. The first part of the demo demonstrated at the notebook index.ipynb, is to look at two scans from the same individual on a different scanner. We register the data of the two sites longitudinally  and then show shape/intensity/geometric differences—potential data sources: GENFI examples. 

### How to link the notebook
[First notebook](https://mybinder.org/v2/gh/HealthBioscienceIDEAS/demon-imaging-harmonisation/HEAD?urlpath=lab/index.ipynb)

## 2nd part : Harmonisation Techniques
Here we apply harmonisation of acquisition and processes using:
* 1st the Simple Linear regression and
* 2nd the COMBAT technique to combine multi-site datasets of multiple individuals at different scanners. 

We demonstrate the advantage of COMBAT. 

The data we analyse include 547 images from 22 different acquisition sites, which include 7 different scanner models of 3 different manufactures and 2 magnetic fields (1.5T and 3T ).
The groups of patients are separated according to the symptoms of Dementia or (Alzheimer’s disease). The data features of the patients include Age, Estimated Year of symptom Onset (EYO), and Total Intervention Volume (TIV).
We look at the difference (variability) in their mean other statistical measures and we compare them.



[Second notebook](https://mybinder.org/v2/gh/HealthBioscienceIDEAS/demon-imaging-harmonisation/HEAD?urlpath=lab/harmonisation.ipynb)

### Harmonisation with Linear Regression 

We Show some basic examples of LR from GENFI. First we add the site as a covariable and fit a LR then. Then we show differences in site between scanners with another LR fitting.

### Harmonisation with COMBAT

We do the same fitting to the site covariance as before using the neuroCombat for more precise harmonisation.

 ### CONCLUSIONS

 ### REFERENCES


# I NEED TO ADD MORE EXPLANATIONS 








