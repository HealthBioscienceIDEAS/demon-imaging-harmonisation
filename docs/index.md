---
layout: default
title: Overview
nav_order: 1
---

# DEMON ECR lecture "Harmonisation strategies for multi-centre imaging studies"
This lecture will cover various techniques for appropriately handling imaging data acquired from multiple sites and scanners. These techniques could be applied for Positron Emission Tomography (PET) imaging and Magnetic resonant imaging (MRI). For simplicity in this lecture, we will be focused on how to apply this to volumetric MRI data.
   Differences in hardware, software and acquisition parameters between MRI scanners can lead to differences in the resulting image data. These differences include:
*	**Resolution differences** in terms of what effective resolution a scanner can acquire data
*	**Intensity/contrast differences** in terms of the signal to noise ratio and contrast between tissue types
*	**Geometric differences** in terms of changes in shape that occur due to various non-linearities in the gradient and shims.
These differences between scanners can ultimately lead to differences in the outcome measures. Methods for reducing or removing these sources of systematic error arising from multiple scanners/sites are called harmonisation. 

This lecture consists of two Jupyter-based notebooks: one giving a brief example of the types of differences that can be observed in the data when acquired on different scanners, and another that looks at various techniques that can be used to harmonise the data and minimise site-related differences.   

During this lecture we will:  
* Give some example differences between scans from a single subject but acquired on a different scanner.
* Show some visualisations of QC and pre-processing metrics that can help identify differences in images caused by change in the MRI scanner.
* Correct for site related effects with simple linear regression-based approach.
* Peform a more advanced harmonisation approach using ComBat, a statistical approach first developed for handling batch effects in genomic analysis and has since been applied many times to multi-site medical imaging data.

## Setup
This lecture is intended to be done as a [Binder-ready repository](https://mybinder.readthedocs.io/en/latest/introduction.html). It takes the [corresponding repository](https://github.com/HealthBioscienceIDEAS/demon-imaging-harmonisation) and builds a VM based on the dependcy/specification needed to run the accompanying Jupyter notebooks. This means the only dependency a user should have is to have a stable network connection and a decent web browser - all of the computing/data will live on the cloud via Binder. 

If you are interested in running this on your local environment, please investigate the local environment page that we will soon put up on this documentation. The dependencies for the local environment are:
* An imaging viewer, such as fsleyes (which can be [integrated into Jupyter notebooks](https://open.win.ox.ac.uk/pages/fsl/fsleyes/fsleyes/userdoc/fsleyes_notebook.html). There are also some Jupyter based alternatives like [niwidgets](https://nipy.org/packages/niwidgets/index.html) and [nanslice](https://github.com/spinicist/nanslice)
*	[nipype](https://nipype.readthedocs.io/en/latest/) - for running registrations in python
*	A registration tool, preferably one like [NiftyReg](https://github.com/KCL-BMEIS/niftyreg) or [ANTs](http://stnava.github.io/ANTs/) that works with Nipype
*	[Pandas](https://pandas.pydata.org/docs/index.html) and [statsmodels](https://www.statsmodels.org/stable/index.html) for doing some of the stastistical analysis and visualisation in Python.
*	[neuroCombat](https://github.com/Jfortin1/neuroCombat) - for running the data harmonisation.


## Datasets
Limited versions of this dataset are only available through these notebooks for educational purposes only, through the kindness of the respective studies. This data is not to be used for research if you require the datasets for research, please contact the relevant data access committees through their standard channels. 
We analyse data from [GENFI](https://www.genfi.org/) and from [ADNI](http://adni.loni.usc.edu/). To investigate the effect of scanner variations in the measurements.

### GENFI
The Genetic Frontotemporal Dementia Initiative (GENFI) is a group of research centres across Europe and Canada with expertise in familial FTD, and is co-ordinated by Dr Jonathan Rohrer at University College London.
The aim of the study is to understand more about genetic FTD, particularly in those who have mutations in the progranulin (GRN), microtubule-associated protein tau (MAPT) and chromosome 9 open reading frame 72 (C9orf72) genes.
GENFI investigates both people who have developed symptoms and also people who have a risk of developing symptoms in the future because they carry an abnormal genetic mutation. By studying these individuals who are destined to develop the disease later in life we can understand the development from the very earliest changes. The key objectives of GENFI are therefore to develop markers which help identify the disease at its earliest stage as well as markers that allow the progression of the disease to be tracked.

### ADNI
In future lessons, we will use data obtained from the [Alzheimer’s Disease Neuroimaging Initiative](https://adni.loni.usc.edu) (ADNI) database. The ADNI was launched in 2003 as a public-private partnership, led by Principal Investigator Michael W. Weiner, MD. The primary goal of ADNI has been to test whether serial magnetic resonance imaging (MRI), positron emission tomography (PET), other biological markers, and clinical and neuropsychological assessment can be combined to measure the progression of mild cognitive impairment (MCI) and early Alzheimer’s disease (AD). For up-to-date information, see www.adni-info.org.

