---
layout: default
title: Introduction
nav_order: 2
---

# Why harmonisation is needed 
Magnetic resonant imaging (MRI) is the standard gold technique for studying the brain's white matter (WM) organization and tissue characteristics. As with many other imaging modalities, MRI images suffer from technical between-scanner variation that hinders comparisons across imaging sites and scanners over time. 

As the number of publicly available neuroimaging databases increases over time, a crucial goal is to combine large-scale imaging studies and improve the statistical analyses to test common biological hypotheses. It is essential to include images of the same subjects from various acquisition sites to meet this goal. 

The main reasons why we need images from multiple acquisition sites from the neuroimaging databases are the following: 
*	We are looking for small but meaningful effect sizes within the image. We can achieve it by reducing the size of the image to include only the region of interest. The benefit is to accommodate in our studies a more extensive sample number AND minimize variability.
*	We need to recruit patients to participate in studies and trials, and this is increasingly competitive, so publicly available multi-site data are convenient to use and cost-effective.
*	With multi-site data, we achieve more representative sampling of the population.

The success of combining multi-site data depends on the comparability of the images across the sites. We need to compare a relatively big sample size which increases variability. 
This variability could be technical across scans, for example, variations in the scanning parameters such as:
*	Different scanning manufactures and differences in  hardware (head coils, gradients, etc.) 
*	Different implementations of sequences between vendors
*	Different parameters between sites.
The variability also could be due to the heterogeneity in the imaging protocol and the different QA procedures.

# How To fix the variability problem
While some of these differences would be measurement error, there are also systematic differences between the sites that would lead to bias and or differences in variability (heteroscedasticity). With harmonisation methods the systematic errors arised from multiple scanners/sites are reduced or removed There are many opportunities for harmonisation. One is tuning the acquisition parameters from the different locations to ensure that the resulting images have properties that are as similar as possible to each other. Another is adaptive processing pipelines that harmonise the images before analysis to adjust these differences between sites/scanners through statistical models. Each approach has its place, with potential benefits and drawbacks, but they can also be used in a combined harmonisation strategy.

## How to link the notebook
[first notebook](https://mybinder.org/v2/gh/HealthBioscienceIDEAS/demon-imaging-harmonisation/HEAD?urlpath=lab/index.ipynb)
