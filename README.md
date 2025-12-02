# A machine-learning photometric classifier for massive stars in nearby galaxies

[working repository]

## Paper I
[arXiv:2203.08125](https://arxiv.org/abs/2203.08125)  

This paper presents the development of a supervised machine-learning classifier designed to identify and classify massive stars in nearby galaxies using multi-band photometry. The model combines optical and infrared photometric data (e.g., Pan-STARRS, 2MASS, Spitzer) and was trained on samples of spectroscopically confirmed sources covering seven main stellar and non-stellar classes: Blue Supergiants (BSG), Yellow Supergiants (YSG), Red Supergiants (RSG), Wolf–Rayet stars (WR), Luminous Blue Variables (LBV), B[e] stars (BeBR), and background galaxies (GAL).

The paper focuses primarily on the methodology, including the feature-space design, training-validation strategy, and the proof of concept applied to a subset of galaxies. 

## Paper II
[arXiv:2504.01232](https://arxiv.org/abs/2504.01232)  

The second paper (Paper II) represents the full-sample application of this classifier to 26 galaxies and provides the most extensive extragalactic catalog of massive-star candidates to date.

## Content

### Running the classifier

A jupyter notebook (Apply_Classifier.ipynb) is provided as a tool to use the classifier. There is a 'test_data' directory with some test data to use (to get an idea of the format for the data). The directory models contain the pretrained models (for SVN, RF, and MLP). 


### Extra plots

In Paper II only a couple of CMDs are presented. Here, we also provide similar plots for all galaxies (check 'Results-CMDs').  


## Installation

You can use conda and the environment.yml file to set up fast and easy an isolated environment to run the classifier. 
