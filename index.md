---
layout: lesson
root: .  # Is the only page that doesn't follow the pattern /:path/index.html
permalink: index.html  # Is the only page that doesn't follow the pattern /:path/index.html
---

Mass spectrometry-based quantitative proteomics data can be representated as a matrix of quantitative values for features (PSMs, peptides, proteins) arranged along the rows, measured for a set of samples, arranged along the columns. The SummarizedExperiment and MultiAssayExperiment classes (Morgan et al. 2020) can handle such data. QFeatures is derived from MultiAssayExperiment.

{% comment %} This is a comment in Liquid {% endcomment %}

> ## Prerequisites
>
> This lesson assumes a working understanding of R.
{: .prereq}

{% include links.md %}
