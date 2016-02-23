*****************
Quick-start Guide
*****************

This guide is a quick walkthrough for the DESeq Browser from start to finish.

Getting Started
===============

First off, we need to head to the DEBrowser webpage at this url:

http://labkey.umassmed.edu/debrowserv2.1/

Once you've made your way to the website, you will be greeted with this tab on the left:

.. image:: debrowser_pics/input_tab.png
	:align: center
	
To begin the DESeq process, you will need to select your Data file (CSV format) to be analyzed using DESeq.

If you do not have a dataset to use, you can use this `demo set <http://bioinfo.umassmed.edu/content/workshops/material/data.tsv>`_

This selection is under the 'Choose CSV File'.

Once you've selected your file and the upload has completed, you will then be able to select your conditions in which you wish to compare using DESeq.

.. image:: debrowser_pics/file_load.png
	:align: center
	
.. image:: debrowser_pics/condition_selection.png
	:align: center
	
Once you've selected your conditions, you can then hit 'Run DESeq!' to begin.

Analyzing The Results
=====================

Once DESeq has finished and the results have been uploaded into DEBrowser, the initial scatterplot of the results will be uploaded.

.. image:: debrowser_pics/scatter_plot.png
	:align: center
	
You can hover over the scatterplot points to display more information about the point selected.  A few bargraphs will be generated for the user to view as soon as a scatterplot point is hovered over.

.. image:: debrowser_pics/bargraph.png
	:align: center
	
.. image:: debrowser_pics/barplot.png
	:align: center
	
You can also select a specific region within the scatter plot and zoom in on the selected window.

.. image:: debrowser_pics/scatter_plot_selection.png
	:align: center
	
Once you've selected a specific region, a new scatterplot of the selected area will appear on the left

.. image:: debrowser_pics/scatter_plot_zoom.png
	:align: center
	
You also have a wide array of options when it comes to fold change cut-off levels, padj cut-off values, and up/down regulated genes.

.. image:: debrowser_pics/filters.png
	:align: center

If you can select the type of plot at the bottom of the filter tab.

.. image:: debrowser_pics/main_plots.png
	:align: center
	
The default is a Scatter plot, but you can also choose from a Volcano plot and a MA plot.

.. image:: debrowser_pics/volcano.png
	:align: center
	
.. image:: debrowser_pics/ma.png
	:align: center

You can download the results in CSV or TSV format by selecting your 'File type' and clicking the 'download' button once you've ran DESeq.

Additional Plots/Tables
=======================

After DESeq has run, and you've had some time to play with the initial plots generated, You may notice the additional tabs above the plots.

.. image:: debrowser_pics/info_tabs.png
	:align: center
	
These tabs display additional plots or tables based on your current padj/fold-change cut-off values.

By selecting additional plots, you will be shown additional plots based on the 'Additional Plots' selection on the left tab.  Additional plots will start off on the All2All plot.

To determine which additional plot you will be viewing, you can select the 'Add.' tab within the filters box to change the types.

.. image:: debrowser_pics/add_plots_opts.png
	:align: center

The first selection, 'All2All', displays an all-to-all plot of your conditions slected.  As you change the padj and fold-change cutt-off values, the data in these plots will also change!

.. image:: debrowser_pics/all2all.png
	:align: center
	
The second additional plot is the heatmap generated based on your dataset.

.. image:: debrowser_pics/heatmap.png
	:align: center

The third plot, the PCA plot (Principal Component Analysis)

.. image:: debrowser_pics/pca.png
	:align: center

In addition to these exciting additional plots, you also have access to the data generated within table form.

The data generated is also sorted based on the following datasets:

* All Detected
* Up Regulated
* Down Regulated
* Selected scatterplot points

.. image:: debrowser_pics/datatable.png
	:align: center
	
The tables contain the following information:

* ID - The specific gene ID
* Sample Names - The names of the samples given and they're corresponding tmm normalized counts
* Conditions - The log averaged values
* padj - padjusted value
* log2FoldChange - The Log2 fold change
* foldChange - The fold change
* log10padj - The log 10 padjusted value

GO Term Tab
===========

The final tab gives the user access to specific GO plots.  Make sure that if you're interested in the GO plots, to switch the tab within the filter box to 'GO'

.. image:: debrowser_pics/go_plots_opts.png
	:align: center
	
Your GO plots include:

* enrichGO - use enriched GO terms
* enrichKEGG - *currently under construction*
* compareClusters - comparison of your clustered data
* Disease - enriched for diseases

After you select what to analyze in your GO plot, then you can select aditional parameters for your GO analysis.

.. image:: debrowser_pics/go_opts.png
	:align: center

The types of plots you will be able to generate include:

* Summary - bar plot
* GOdotplot - dot plot
* enrichMap - *currently under construction*

Once you have adjusted all of your parameters, you may hit the submit button in the top right and then wait for the results to show on screen!

Example Summary plot:

.. image:: debrowser_pics/go_summary.png
	:align: center

Example GOdotplot:

.. image:: debrowser_pics/go_dot_plot.png
	:align: center
	
Now you can enjoy all of the analysis tools within DEBrowser!
