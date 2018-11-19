<img src="vignettes/fig/header.png" align="right"/>

Description
===========

This package provides an interactive graphical user interface (GUI) for RNA-seq data differential expression (DE), differential alternative splicing (DAS) and differential transcript usage (DTU) analyses based on two popular pipelines: limma and edgeR. The 3DRNAseq GUI is based on R shiny App and enables command-line-free analysis. To perform analysis, the first step is to generate transcript quantification from quantification tools, such as Salmon and Kallisto. Then users can do mouse click on the App to upload transcript read counts, perform DE and DAS analysis, and make beautiful plots, e.g. expression mean-variance trend plots, PCA plots, heatmap, GO annotation plots, etc. The GUI has steps of proper data pre-processing and false positive controls. These lead to robust DE DAS predictions. All the results and plots can be saved to a report in html, pdf or word format. The analysis pipeline has been successfully used in different RNA-seq studies from Arabidopsis, barley and potato.

Installation and loading
========================

``` r
############################################################
## use devtools R package to install ThreeDRNAseq from Github
##---> If devtools is not installed, please install
if(!'devtools' %in% installed.packages()[,"Package"])
  install.packages('devtools')

devtools::instasll_github('wyguo/ThreeDRNAseq')

############################################################
## Install packages of dependency
```