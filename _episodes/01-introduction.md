---
title: "Introduction to quantitative proteomics data"
teaching: 15
exercises: 0
questions:
- "What data do we have?"
- "What analyses can we apply?"
- "How can we check the data throughout the analysis?"
objectives:
- "Understand proteomics data set."
- "Understand what data cleaning we need to do."
- "Understand what data analysis we can do."
keypoints:
- "It’s important to understand your proteomics data."
---

## Data 
  - The data we are going to use are part of a study 
  of the Clinical Proteomic Technology Assessment for Cancer
  [CPTAC](https://pubmed.ncbi.nlm.nih.gov/19858499/)
  led by Amanda Paulovich. 
   
  - In the experiment, the authors spiked the Sigma Universal 
  Protein Standard mixture 1 (UPS1) containing 48 different human
  proteins in a protein background of 60 ng/μL S. cerevisiae strain BY4741. 
  Two different spike-in concentrations were used: 6A 
  (0.25 fmol UPS1 proteins/μL) and 6B (0.74 fmol UPS1 proteins/μL).  
  
  - The data were searched with MaxQuant version 1.5.2.8, and detailed search settings were described by [Goeminne et al](https://pubmed.ncbi.nlm.nih.gov/26566788/). 
  
  - Three replicates are available for each concentration. The study is a spike-in study for which we know the ground truth so we have the ability to evaluate the quality of the fold change estimates and the list of DE genes that we return with a method.

{% include links.md %}

## Read data 

To read and instepct the peptides.txt file we will use the package `readr`, which is bundled within the `tidyverse` package. Please load the `tidyverse` if not already done. : 

~~~
library("tidyverse")
~~~
{:.language-r}

~~~
f <- readr::read_delim("https://raw.githubusercontent.com/lgatto/bioc-ms-prot/master/data/cptac_peptides.txt",delim="\t")

## explore
head(f)
~~~
{:.language-r}

## Quantitative information

Quantitative information is contained in the columns that have "Intensity" tag. We can see which columns have quantitative information.
~~~
(i <- grep("Intensity.", names(f))) # 56 57 58 59 60 61
~~~
{:.language-r}

### Your turn

> ## Exercise
>
> Subtract peptide names and intensity values from `f`.
> > ## Solution
> > `f[,c(1,i)]`       
> >
> {: .solution}
{: .challenge} 
