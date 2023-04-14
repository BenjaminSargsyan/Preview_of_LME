# Diffuse Large B cell lymphoma Microenvironment classification

## Introduction

Diffuse  large  B-cell  lymphoma  (DLBCL)  is  a  biologically  and  clinically  heterogene- ous  disease.  Transcriptomic  and  genetic  characterization  of  DLBCL  has  increased  the  understanding  of  its  intrinsic  pathogenesis  and  provided  potential  therapeutic  targets. Besides the classification of the DLBCL the Lymphoma Microenvironment (LME) classification also plays a critical role in further clinical outcomes and response to the therapies. Current repository gives an opportunity to analyze the  and understand which LME subtype it belongs to. Analysis are based on the ssGSEA scores of the 25 Functional Gene expression signatures where each of them correspond to a specific cell type or biological process.
Each of the classified subtypes has its unique group of FGES which is presented on the figure below.

![LME classification related materials (2)](https://user-images.githubusercontent.com/127855909/230941453-041a44b2-b068-4000-ba78-eb3e20accce1.jpg)

In BostonGene, we developed a way to create samples Molecular Functional Portrait which is a planetary schematic representation of integrated molecular and functional characteristics of a tumor and its microenvironment that depicts LME subtype, and the activity of tumor promoting and suppressing processes. The portrait includes qualitative and quantitative descriptions of modules built based on the expression of BostonGene curated 25 Fges as it was mentioned earlier (reference manuscript and table), with the size of each module corresponding to the intensity of the normalized single-sample gene set enrichment analysis (ssGSEA) score, and the colors denoting pro- (red) or anti- (blue) cancer activity .A short introduction to each LME subtype with its MFP portrait and overall survival predictions you can see on figure below.

![image](https://user-images.githubusercontent.com/127855909/230941931-c1ab7abf-d5df-44f8-9307-2b4cf7bb81af.png)

## Citation
This repository and all of its content are linked to “Clinical and Biological Subtypes of B-cell Lymphoma Revealed by Microenvironmental Signatures” article. For the article look in the link below:


https://www.cell.com/cancer-cell/fulltext/S1535-6108(21)00222-1



For more information visit to BostonGene’s scientific portal using the following link:  https://science.bostongene.com/tumor-portrait/ 
Please, when using the provided materials for research and publication make a reference to this repository and the article.

## Setup
If your environment is already set up according to the requirements in the description of Setup.md file, you only just have to clone the github repository and start your analysis.
Copy the command below to clone our repository into your environment 
git clone https://github.com/BostonGene/LME

## Implementation overview
**Note: Please be aware that the analysis are developed only for DLBCL type of lymphomas and the input expression matrix data must be RNA-Seq type otherwise the analysis won't work properly.**

To have a better understating of how the analysis work below you can see the corresponding scheme of the flow:

![LME classification flowchart](https://user-images.githubusercontent.com/127855909/230636947-bac5b972-e485-4be0-9330-67b058613d5d.jpg)


All of the analyses are contained in [LME_Classification](LME_Classification.ipynb) notebook. Overall notebook is divided into separate sections each of having their own subsections. Below you can see the main navigation and functionality of the analyses flow:


* Data preparation
  * Loading gene signatures
  * Loading reference cohort annotation file
  * Loading the reference cohort
* Confirming that reference cohort does not have any batch effects
  * Creating a KNN model based on the reference cohort
* Preparation and QC of gene expression matrix
  * Read the gene expression matrix
  * Quality check for the example data
    * Batch effect detection
    * Outlier detection
    * Data distribution check
* Classification of the gene expression data
  * Calculating ssGSEA and PROGENy scores of signatures
  * Classifying the example cohort
  
  
**Notice that all of the steps are essential and you can’t skip any of them.**
