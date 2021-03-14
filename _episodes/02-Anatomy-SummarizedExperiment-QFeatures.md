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


# Anatomy of a QFeatures object
QFeatures objects form [QFeatures package](hhttp://www.bioconductor.org/packages/release/bioc/html/QFeatures.html) are based on the `SummarizedExperiment` and `MultiAssayExperiment` classes and provides infrastructure to manage and analyse quantitative features from mass spectrometry experiments. It follows a hierarchical structure: *spectra* compose  *peptides* which in turn compose *proteins*. The main advantage of this structure is that is very easy to  navigate across spectra, peptide and protein quantitative data.

<a href="{{ page.root }}/fig/SE.png">
  <img src="{{ page.root }}/fig/QF.png" alt="QFeatures" />
</a>
