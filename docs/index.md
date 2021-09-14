---
layout: default
title: Overview
nav_order: 1
---

# DEMON ECR lecture "Harmonisation strategies for multi-centre imaging studies"
This lecture will cover various techniques for appropriately handling imaging data acquired from multiple sites and scanners. These techniques could be applied for Positron Emission Tomography (PET) imaging and Magnetic resonant imaging (MRI). For simplicity in this lecture, we will be focused on MRI and use the corresponding data.
   Differences in hardware, software and acquisition parameters between MRI scanners can lead to differences in the resulting image data. These differences include:
*	Resolution differences in terms of what effective resolution a scanner can acquire data
*	Intensity/contrast differences in terms of the signal to noise ratio and contrast between tissue types
*	Geometric differences in terms of changes in shape that occur due to various non-linearities in the gradient and shims.
These differences between scanners can ultimately lead to differences in the outcome measures. Methods for reducing or removing these sources of systematic error arising from multiple scanners/sites are called harmonisation. 

We present harmonisation methods of correcting the imaging outcome and the measurements of an individual scanned at a site A and then again, the next day at site B. The multi-site acquisition induces different in the initial measurements which are minimised with the harmonisation procedure. 
We also show how advanced harmonisation techniques could lead to more precise (accurate???) measurements of multiple subjects, scanned at different sites with different scanners and technical parameters  


During this lecture we will:  
*	 Give some example differences between scans from a single subject but acquired on a different scanner.
*	 Show some visualisations of QC and pre-processing metrics that can help identify.
*	 Do a more advanced harmonisation approach using Combat. This is demonstrated using multiple subjects and acquiring their scans at many different sites using three different scanner manufacturers and two magnetic field intensities.
*	Do a simple linear regression where the site is included as a covariate.

## Setup
This lecture is intended to be a Binder-ready repository (add links to Binder). This means that the repository with the Jupyter notebook will created as a Docker container and then accessible via the web. Thus, it should not require any more requirements than a network connection.
If you are interested in running this on your local environment, please investigate the local environment page. The dependencies will be:
* fsleyes - for viewing images within the notebook - if possible, otherwise use matplotlib or other image plotting libary
*	niftyreg (C++) - for doing image registration
*	nipype - for running registrations in python
*	Python package for linear regression (pandas,scikit-learn?)
*	ComBat - for running harmonisation
The lecture will be in two parts with their corresponding Jupiter notebooks.

## Datasets
Limited versions of this dataset are only available through these notebooks for educational purposes only, through the kindness of the respective studies. This data is not to be used for research if you require the datasets for research, please contact the relevant data access committees through their standard channels. 
We analyse data from GENFI and from ADNI. To investigate the effect of scanner variations in the measurements
The Genetic Frontotemporal Dementia Initiative (GENFI) is a group of research centres across Europe and Canada with expertise in familial FTD, and is co-ordinated by Dr Jonathan Rohrer at University College London.
The aim of the study is to understand more about genetic FTD, particularly in those who have mutations in the progranulin (GRN), microtubule-associated protein tau (MAPT) and chromosome 9 open reading frame 72 (C9orf72) genes.
GENFI investigates both people who have developed symptoms and also people who have a risk of developing symptoms in the future because they carry an abnormal genetic mutation. By studying these individuals who are destined to develop the disease later in life we can understand the development from the very earliest changes. The key objectives of GENFI are therefore to develop markers which help identify the disease at its earliest stage as well as markers that allow the progression of the disease to be tracked.

Data used in the preparation of this lesson were obtained from the Alzheimer’s Disease Neuroimaging Initiative (ADNI) database (adni.loni.usc.edu). The ADNI was launched in 2003 as a public-private partnership, led by Principal Investigator Michael W. Weiner, MD. The primary goal of ADNI has been to test whether serial magnetic resonance imaging (MRI), positron emission tomography (PET), other biological markers, and clinical and neuropsychological assessment can be combined to measure the progression of mild cognitive impairment (MCI) and early Alzheimer’s disease (AD). For up-to-date information, see www.adni-info.org.









