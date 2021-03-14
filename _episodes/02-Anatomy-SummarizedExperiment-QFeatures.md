---
title: "Identifying the anatomy of SummarizedExperiment and QFeatures objects"
teaching: 30
exercises: 20
questions:
- "How do SummarizedExperiment and QFeatures objects look like?"
objectives:
- "Recognize the anatomy of SummarizedExperiment and QFeatures objects."
- "Execute common operations on SummarizedExperiment and QFeatures objects."
---

# Anatomy of a SummarizedExperiment object
These are the component pieces of the `SummarizedExperiment` for data representation.

<a href="{{ page.root }}/fig/SE.png">
  <img src="{{ page.root }}/fig/SE.png" alt="SummarizedExperiment" />
</a>

We can access different levels of information of a SummarizedExperiment object using the following functions:
- assay()): A matrix-like or list of matrix-like objects of identical dimension
- colData(): Annotations on each column, as a DataFrame.
- rowData() and / or rowRanges(): Annotations on each row.



# Anatomy of a QFeatures object
QFeatures objects form [QFeatures package](hhttp://www.bioconductor.org/packages/release/bioc/html/QFeatures.html) are based on the `SummarizedExperiment` and `MultiAssayExperiment` classes and provides infrastructure to manage and analyse quantitative features from mass spectrometry experiments. It follows a hierarchical structure: *spectra* compose  *peptides* which in turn compose *proteins*. The main advantage of this structure is that is very easy to  navigate across spectra, peptide and protein quantitative data.

<a href="{{ page.root }}/fig/SE.png">
  <img src="{{ page.root }}/fig/QF.png" alt="QFeatures" />
</a>

We can load a simplify example `feat1`  data, which is composed of single *assay* of class `SummarizedExperiment` composed of 10 rows and 2
columns.

~~~
library("QFeatures")
data(feat1)
feat1
~~~
{:.language-r}

Similarly to what we have done for `SummarizedExperiment` object , we can extract information from QFeatures

~~~
colData(feat1)
assay(feat1[[1]])
rowData(feat1[[1]])
~~~
{:.language-r}


