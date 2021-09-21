# DEMON ECR lecture "Harmonisation strategies for multi-centre imaging studies"

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/HealthBioscienceIDEAS/demon-imaging-harmonisation/HEAD)

## Overview
This lecture will cover various techniques for how to handle variability in imaging data arising from multi-site and multi-scaner acquisition. 
Differences in hardware, software and acquisition parameters between scanners can lead to diferences in the resulting image data. This lecture was developed as part of the [Health and Bioscience IDEAS training programme](https://healthbioscienceideas.github.io/), funded by [UKRI Innovation Scholars (MR/V03863X/1)](https://www.ukri.org/opportunity/innovation-scholars-data-science-training-in-health-bioscience/)
These differences include:

* _Resolution differences_ in terms of what effective resolution a scanner is able to acquire data
* _Intensity/contrast differences_ in temrs of the signal to noise ratio and contrast between tissue types
* _Geometric differences_ in terms of changes in shape that occur due to various non-linearities in the gradient and shims.

These differences between scanners can ultimately lead to differences in the outcome measures, so if an individual
was scanned at site A and then again the next day at site B, there would be potential differences in the measurement.
While of course some of these differences would simply be measurement error, there are also systematic differences between the sites that would lead
to bias and/or differences in variability (heteroskedasticity). 
Methods that reduce or remove these sources of systematic error arising from multiple scanners/sites while leaving the biologically-relevant changes intact are often referred to as data harmonisation. 
There are many opportunities for harmonisation, from prospecitvely tuning the acquisition parameters from the different sites 
to ensure that the resulting images have properties that are as similar as possible to each other, to adaptive processing pipelines
that harmoinse the images before analysis to adjusting for these differences between sites/scanners through statsitical models.
Each approach has its place, with potential benefits and drawbacks, but they can also be used in a combined harmonisation strategy.

In the Jupyter notebook lectures included in this repository, we will:
* Give some example differences between scans from a single subject but acquired on a different scanner
* Show some visualisations of QC and pre-processing metrics that can help identify 
* Do a simple linear regression where site is included as a covariate
* Do a more advanced harmonisation approach using Combat

## Setup
This lecture is intended to be a [Binder-ready](https://mybinder.org/) repository (add links to Binder). This means that the repository with the Jupyter notebook will created as a 
Docker container and then accessible via the web. Thus it should not require any more requirements than a network connection and web browser.

If you are intereste in running this on your local environment, please investigate the local ennvironment page. The dependencies will be: 
* [NiftyReg](https://github.com/KCL-BMEIS/niftyreg) (C++) - a lightweight, robust image registration tool
* [nipype](https://nipype.readthedocs.io/en/latest/) - for running registrations in python
* [Pandas](https://pandas.pydata.org/docs/index.html) and [statsmodels](https://www.statsmodels.org/stable/index.html) for doing some of the stastistical analysis and visualisation in Python.
* [nanslice](https://github.com/spinicist/nanslice) for a simple medical imaging viewer in the notebook.
* [ComBat](https://github.com/Jfortin1/ComBatHarmonization) - for running harmonisation

Thanks to the team behind the Software Carpentries courses on [Introduction to Working with MRI Data in Python](https://carpentries-incubator.github.io/SDC-BIDS-IntroMRI) and other great courses on neuro MRI for their inspiration on how to setup teaching material in this manner. 
