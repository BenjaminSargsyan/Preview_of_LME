## Introduction

Diffuse  large  B-cell  lymphoma  (DLBCL)  is  a  biologically  and  clinically  heterogene- ous  disease.  Transcriptomic  and  genetic  characterization  of  DLBCL  has  increased  the  understanding  of  its  intrinsic  pathogenesis  and  provided  potential  therapeutic  targets. Besides the classification of the DLBCL the Lymphoma Microenvironment (LME) classification also plays a critical role in further clinical outcomes and response to the therapies. Current repository gives an opportunity to analyze LME and understand which LME subtype it belongs to. Analysis are based on the ssGSEA scores of the 25 Functional Gene expression signatures where each of them correspond to a specific cell type or biological process.
Each of the classified subtypes has its unique group of FGES which is presented on the figure below.

(Table or Picture for each subtype with its signatures group will be ready at the end of the week)


In BostonGene, we developed a way to create samples Molecular Functional Portrait which is a planetary schematic representation of integrated molecular and functional characteristics of a tumor and its microenvironment that depicts LME subtype, and the activity of tumor promoting and suppressing processes. The portrait includes qualitative and quantitative descriptions of modules built based on the expression of BostonGene curated 25 Fges as it was mentioned earlier (reference manuscript and table), with the size of each module corresponding to the intensity of the normalized single-sample gene set enrichment analysis (ssGSEA) score, and the colors denoting pro- (red) or anti- (blue) cancer activity .A short introduction to each LME subtype with its MFP portrait and overall survival predictions you can see on figure below.


(Picture Like in the TME Haven’t found yet)







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
Note: Please be aware that the analyses are developed only for DLBCL type of lymphomas.
To have a better understating of how the analysis work below you can see the corresponding scheme of the flow:



All of the analyses are contained in LME_Classification.ipynb notebook. Overall notebook is divided into separate sections each of having their own subsections. Below you can see the main navigation and functionality of the analyses flow:


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
  
  
**Notice that all of the steps are essential and you can’t skip any of them.
