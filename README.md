# Diffuse Large B cell lymphoma Microenvironment classification

## Introduction

Diffuse large B-cell lymphoma (DLBCL) is a biologically and clinically heterogeneous disease. Transcriptomic and genetic characterization of DLBCL has increased the understanding of its intrinsic pathogenesis and provided potential therapeutic targets. Besides the classification of the DLBCL, the Lymphoma Microenvironment (LME) classification also plays a critical role in patient clinical outcomes and response to antineoplastic therapies. The current repository gives an opportunity to analyze the gene expression data and understand which LME subtype it belongs to. The analysis is based on the ssGSEA scores of the 25 functional gene expression signatures, each of them corresponding to a specific cell type or biological process. Each LME subtype is characterized by a unique set of FGES, shown in Fig. 1.

![Table](https://github.com/BenjaminSargsyan/Preview_of_LME/assets/127855909/a0799528-5aa2-48f1-bd84-580b214da1fa)


<p align="center">Fig. 1. LME subtypes with their definitive functional gene expression signatures</p>

<p align="center">A brief description of each LME type and its graphical interpretation are provided in Fig. 2.</p>

![image](https://user-images.githubusercontent.com/127855909/230941931-c1ab7abf-d5df-44f8-9307-2b4cf7bb81af.png)

<p align="center">Fig. 2. LME subtypes and their brief descriptions</p>


## Citation
If software, data, and/or website are used in your publication, please cite [Kotlov N et al. Clinical and Biological Subtypes of B-cell Lymphoma Revealed by Microenvironmental Signatures. Cancer Discov. 2021;11(6):1468–1489](https://aacrjournals.org/cancerdiscovery/article/11/6/1468/666622/Clinical-and-Biological-Subtypes-of-B-cell) and make a reference to this repository.


For more information visit [BostonGene's scientific portal.](https://science.bostongene.com/tumor-portrait/)


## Setup
Set up your environment according to the requirements in the description of the Setup.md file in the repository.
If your environment is already set up accordingly, clone the Github repository to start your analysis:
    git clone https://github.com/BostonGene/LME

## Implementation overview
**Note: The analysis was developed for DLBCL only**

The analysis workflow is presented in the diagram below, highlighting the main steps and logical elements of the notebook.

![Scheme](https://github.com/BenjaminSargsyan/Preview_of_LME/assets/127855909/83bf38a5-c55f-420e-b6df-153e21144a1e)

**Note: Only RNA-Seq data can be used as input data for the analysis.**

All the analyses are performed in the [LME_Classification.ipynb](LME_Classification.ipynb) notebook. The notebook is divided into three separate sections with several subsections within them. Below you can see the main navigation and functionality of the analysis flow:



* Data preparation
  * Load the reference cohort
  * Check the reference cohort for batch effects
  * Load gene signatures
* Gene expression matrix preparation and QC
  * Read example data gene expression
  * Check the quality of the example data
    * Batch effect detection
    * Batch effect detection by PCA
    * Outlier detection
    * Data distribution check
* Classification of SAMPLE_EXPRESSION
  * Create a KNN model based on the reference cohort
  * Calculate ssGSEA and PROGENy scores of signatures
  * Classify the example cohort
  
  
***Note: All of the listed steps are essential. Do not skip any of them.***
