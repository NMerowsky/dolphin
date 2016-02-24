***********
DESeq Guide
***********

This guide contains a breif discription of DESeq2 used within the DEBrowser

Getting Started
===============

Sample pooling has revolutionized sequencing. It is now possible to sequence 10s of samples together. Different objectives require different sequencing depths.
Conducting differential gene expression analysis requires less sequencing depth than transcript reconstruction so when pooling samples it is critical to keep the objective of the experiment in mind.


What is DESeq2?
===============

The goal of Differential gene expression analysis is to find genes or transcripts whose difference in expression, when accounting for the variance within condition, is higher than expected by chance.

`DESeq <https://bioconductor.org/packages/release/bioc/html/DESeq2.html>`_ is an R package available via Bioconductor and is designed to normalize count data from high-throughput sequencing assays such as RNA-Seq and test for differential expression.

DESeq2 uses a negative binomial distribution model when calculating differential expression.

For more information on the DESeq2 algorithm, you can visit `this website <https://bioconductor.org/packages/release/bioc/vignettes/DESeq2/inst/doc/DESeq2.pdf>`_

Getting Started
===============

In order to conduct differential expression analysis, we first need data to analyze.  In order to call DESeq2, we're going to need gene quantifications and expected counts for those genes.

To obtain these quantifications, we typically use `RSEM <http://deweylab.github.io/RSEM/>`_, however there are other ways to obtain this data.

The TSV files used to describe the quantification counts are similar to this:

gene	transcript	exper_rep1	exper_rep2	exper_rep3	control_rep1	control_rep2	control_rep3
DQ714826	uc007tfl.1	0.00	0.00	0.00	0.00	0.00	0.00
DQ551521	uc008bml.1	0.00	0.00	0.00	0.00	0.00	0.00
AK028549	uc011wpi.1	2.00	1.29	0.00	0.00	0.00	1.40

Where the gene column represent the gene name, the transcript column represents the transcript(s) name (comma separated for multiple), and the rest of the columns are the counts for your samples.

DESeq2 Workflow
==============

DESeq2 performs multiple steps in order to analyze the data you've provided for it.

The first step is to indicate the condition that each column (experiment) in the table represent.

You can group multiple samples into one condition column.

DESeq will compute the probability that a gene is differentially expressed (DE) for ALL genes in the table. It outputs both a nominal and a multiple hypothesis corrected p-value (padj).

