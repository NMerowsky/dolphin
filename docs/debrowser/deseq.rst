***************
DESeq/DEBrowser
***************

This guide contains a breif discription of DESeq2 used within the DEBrowser


Introduction
============

Differential gene expression analysis has become an increasingly popular tool
in determining and viewing up and/or down experssed genes between two sets of
samples.  The goal of Differential gene expression analysis is to find genes
or transcripts whose difference in expression, when accounting for the
variance within condition, is higher than expected by chance.  `DESeq2
<https://bioconductor.org/packages/release/bioc/html/DESeq2.html>`_ is an R
package available via Bioconductor and is designed to normalize count data
from high-throughput sequencing assays such as RNA-Seq and test for
differential expression (Love et al. 2014).  For more information on the
DESeq2 algorithm, you can visit `this website <https://bioconductor.org/packages/release/bioc/vignettes/DESeq2/inst/doc/DESeq2.pdf>`_  With multiple parameters such as
padjust values, log fold changes, and plot styles, altering plots
created with your DE data can be a hassle as well as time consuming.  The
Differential Expression Browser uses DESeq2 coupled with shiny to produce
real-time changes within your plot queries and allows for interactive browsing
of your DESeq results. In addition to DESeq analysis, DEBrowser also offers
a variety of other plots and analysis tools to help visualize your data
even further.


Getting Started
===============

In order to conduct differential expression analysis, we first need data to analyze.  In order to call DESeq2, we're going to need
gene quantifications and expected counts for those genes.

To obtain these quantifications, we typically use `RSEM <http://deweylab.github.io/RSEM/>`_, however there are other ways to obtain this data.
The TSV file is used to describe the quantification counts. Counts can be recorded as raw counts, RPKM values, or TMM values just as long as
all of the counts are recorded in the same value type.  Each of the columns in the TSV represent:

* *gene*: Gene name
* *transcript*: Transcript(s) name assoiated with this gene (comma seperated for multiple)
* *sample names*: The RPKM count for this sample

You can have multiple samples within your TSV file, as long as there is a count that will represent that sample within each row.
You can view our demo data `here`_ as an example for creating you own dataset.

.. _here: http://bioinfo.umassmed.edu/content/workshops/material/data.tsv

DESeq2 Workflow
===============

DESeq2 performs multiple steps in order to analyze the data you've provided for it.

The first step is to indicate the condition that each column (experiment) in the table represent.

You can group multiple samples into one condition column.

DESeq2 will compute the probability that a gene is differentially expressed (DE) for ALL genes in the table. It outputs

both a nominal and a multiple hypothesis corrected p-value (padj) using a negative binomial distribution.

DEBrowser
=========

DEBrowser utilizes `Shiny <http://shiny.rstudio.com/>`_, a R based application development tool that creates a wonderful interactive user interface (UI)

combinded with all of the computing prowess of R.  After the user has selected the data to analyze and has used the shiny

UI to run DESeq2, the results are then input to DEBrowser.  DEBrowser manipulates your results in a way that allows for

interactive plotting by which changing padj or fold change limits also changes the displayed graph(s).

For more details about these plots and tables, please visit our quickstart guide for some helpful tutorials.

References
==========

1. Love MI, Huber W and Anders S (2014). Moderated estimation of fold change and
    dispersion for RNA-seq data with DESeq2.  Genome Biology, 15, pp. 550.
    http://doi.org/10.1186/s13059-014-0550-8.

