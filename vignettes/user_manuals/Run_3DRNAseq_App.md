---
title: "Run 3DRNAseq App"
author: "Wenbin Guo"
date: "9 December 2018"
output:
  md_document:
    toc: true
    preserve_yaml: true
    variant: markdown_github
vignette: >
  %\VignetteEngine{knitr::rmarkdown}
---

-   [Install dependency packages](#install-dependency-packages)
-   [Download example data](#download-example-data)
-   [Run ThreeDRNAseq App](#run-threedrnaseq-app)

Install dependency packages
---------------------------

It is recommended to run the 3D RNA-seq App using RStudio with R version &gt; 3.5.0. It takes about 10 min to install if all packages are missing from your PC.

``` r
#######################################################################################################
## Install packages of dependency
###---> Install packages from Cran
cran.package.list <- c('shiny','shinydashboard','rhandsontable','shinyFiles','shinyjs','DT',
                       'plotly','ggplot2','eulerr','ggrepel','statmod',
                       'gridExtra','fastcluster','rmarkdown')
for(i in cran.package.list){
   if(!(i %in% rownames(installed.packages()))){
     message('Installing package: ',i)
     install.packages(i,dependencies = T)
   } else next
}

###---> Install packages from Bioconductor
bioconductor.package.list <- c('tximport','edgeR','limma','RUVSeq','ComplexHeatmap','rhdf5')
for(i in bioconductor.package.list){
  if (!requireNamespace("BiocManager", quietly = TRUE))
    install.packages("BiocManager")
  if(!(i %in% rownames(installed.packages()))){
    message('Installing package: ',i)
    BiocManager::install(i, version = "3.8",dependencies = T)
  } else next
}
```

Download example data
---------------------

The example.zip file can be download from: <https://github.com/wyguo/ThreeDRNAseq/raw/master/vignettes/example.zip>. Save the data to local folder and unzip it.

Run ThreeDRNAseq App
--------------------

``` r
library(shiny)
runGitHub(repo = 'ThreeDRNAseq',username = 'wyguo',subdir = 'app')
```