# A machine-learning photometric classifier for massive stars in nearby galaxies

This is a collection of notebooks, data, and results obtained with the Photometric Classifier 4 MAssive Stars (developed through the  [ASSESS project](https://assess.astro.noa.gr/)). The idea behind this project was to develop a supervised machine-learning classifier designed to identify and classify massive stars in nearby galaxies using multi-band photometry. 

Paper I focused primarily on the methodology, including the feature-space design, training-validation strategy, and the proof of concept applied to a subset of galaxies. In Paper II, we applied it to a large sample of sources from 26 galaxies, where we also carefully selected optimal candidates to examine the trends of different populations of massive stars with metallicity. It als provides the most extensive extragalactic catalog of massive-star candidates to date.

## Paper I
[Maravelias et al. 2022, A&A, 666, A122, (arXiv:2203.08125)](https://arxiv.org/abs/2203.08125)

*Abstract:* Mass loss is a key parameter in the evolution of massive stars, with discrepancies between theory and observations and with unknown importance of the episodic mass loss. To address this we need increased numbers of classified sources stars spanning a range of metallicity environments. We aim to remedy the situation by applying machine learning techniques to recently available extensive photometric catalogs. We used IR/Spitzer and optical/Pan-STARRS, with Gaia astrometric information, to compile a large catalog of known massive stars in M31 and M33, which were grouped in Blue, Red, Yellow, B[e] supergiants, Luminous Blue Variables, Wolf-Rayet, and background galaxies. Due to the high imbalance, we implemented synthetic data generation to populate the underrepresented classes and improve separation by undersampling the majority class. We built an ensemble classifier using color indices. The probabilities from Support Vector Classification, Random Forests, and Multi-layer Perceptron were combined for the final classification. The overall weighted balanced accuracy is ~83%, recovering Red supergiants at ~94%, Blue/Yellow/B[e] supergiants and background galaxies at ~50-80%, Wolf-Rayets at ~45%, and Luminous Blue Variables at ~30%, mainly due to their small sample sizes. The mixing of spectral types (no strict boundaries in their color indices) complicates the classification. Independent application to IC 1613, WLM, and Sextans A galaxies resulted in an overall lower accuracy of ~70%, attributed to metallicity and extinction effects. The missing data imputation was explored using simple replacement with mean values and an iterative imputor, which proved more capable. We also found that r-i and y-[3.6] were the most important features. Our method, although limited by the sampling of the feature space, is efficient in classifying sources with missing data and at lower metallicitites. 

## Paper II
[Maravelias et al. 2026, A&A, 709, A218, (arXiv:2504.01232)](https://arxiv.org/abs/2504.01232) 

*Abstract:* Mass loss is a key aspect of stellar evolution, particularly in evolved massive stars, yet episodic mass loss remains poorly understood. To investigate this, we need evolved massive stellar populations across various galactic environments. However, spectral classifications are challenging to obtain in large numbers, especially for distant galaxies. We addressed this by leveraging machine-learning techniques. We combined Spitzer photometry and Pan-STARRS1 optical data to classify point sources in 26 galaxies within 5 Mpc, and a metallicity range 0.07-1.36 Z⊙. Gaia data release 3 (DR3) astrometry was used to remove foreground sources. Classifications are derived using a machine-learning model developed in our previous work. We report classifications for 1,147,650 sources, with 276,657 sources (~24%) being robust. Among these are 120,479 red supergiants (RSGs; ~11%). The classifier performs well even at low metallicities (~0.1 Z⊙) and distances under 1.5 Mpc, with a slight decrease in accuracy beyond ~3 Mpc due to Spitzer's resolution limits. We also identified 21 luminous RSGs (log(L/L⊙)≥5.5), 159 dusty yellow hypergiants in M31 and M33, as well as 6 extreme RSGs (log(L/L⊙)≥6) in M31, challenging observed luminosity limits. Class trends with metallicity align with expectations, although biases exist. This catalog serves as a valuable resource for individual-object studies and James Webb Space Telescope target selection. It enables the follow-up on luminous RSGs and yellow hypergiants to refine our understanding of their evolutionary pathways. Additionally, we provide the largest spectroscopically confirmed catalog of extragalactic massive stars and candidates to date, beyond the Clouds, comprising 5,273 sources (including ~330 other objects). 

## Content

### Train data

This folder contains the initial collection of M31 and M33 (1077) sources used for training (M31+M33\_spt\_final\_mod.csv), along with the dataset (932 sources) on which the classifier was actually trained (M31+M33\_spt\_final\_cleared\_.csv). 

The latter file was produced by first removing all objects without values in r, i, z, y, [3.6], and [4.5] bands and their corresponding errors, then creating the corresponding color indexes (r-i, i-z, z-y, y-[3.6], [3.6]-[4.5]), and finally assigning a broader spectral class (that the original one - see paper for details). 

### Running the classifier

A jupyter notebook (Apply\_Classifier.ipynb) is provided as a tool to use the classifier. There is a 'test_data' directory with some test data to use (to get an idea of the format for the data). The directory models contain the pretrained models (for SVN, RF, and MLP). 


### Extra plots

In Paper II only a couple of CMDs are presented. Here, we also provide similar plots for all galaxies (check 'Results-CMDs'). 


## Installation

You can use conda and the environment.yml file to set up fast and easy an isolated environment to run the classifier. 
