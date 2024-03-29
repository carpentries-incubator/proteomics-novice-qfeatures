---
title: "Importing txt into Qfeatures"
teaching: 15
exercises: 0
questions:
- "How can we import txt file into QFeatures object?"
- "How can we add metadata to QFeatures?"
- "How can we inspect QFeatures features?"
objectives:
- "Import MaxQuant peptides.txt file into QFeatures object."
- "Inspect QFeatures features."
keypoints:
- "Functions from QFeatures and SummarizeExperiment packages allow to do these steps seamlessly."
---

## Read peptide file into QFeatures

We can use the `readQFeatures` function from `QFeatures` package to import `f` data.frame that we read into R before. We also need to provide the position `i` where our quantitative Intensity columns live.  We can name this new `QFeatures` object `cptac`. 
~~~
library("QFeatures")
cptac <- readQFeatures(f, ecol = i, sep = "\t", name = "peptides", fnames = "Sequence")
~~~
{:.language-r}
> ## Exercise
>
> Use the `colData` function to see description of each sample from `cptac`
>
> > ## Solution
> > `colData(cptac)`        
> >
> {: .solution}
{: .challenge}  
## Encode the experimental design in QFeatures
We can update the sample (column) annotations to encode the two
groups, 6A and 6B, and the original sample numbers.
~~~
ptac$group <- rep(c("6A", "6B"), each = 3)
cptac$sample <- rep(7:9, 2)
colData(cptac)
~~~
{:.language-r}
## Get metadata information of QFeatures
We can get metadata information of QFeatures
~~~
rowData(cptac)
~~~
{:.language-r}
We can use the `assay` function to get a matrix-like `cptac`
~~~
library("magrittr")
assay(cptac) %>% head(2)
~~~
{:.language-r}
