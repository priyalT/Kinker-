Description
===========


This is the project based on the Figure 1 Lab (F1Lab) internship emulator set up by Dean Lee. We dive into the intricacies of the Kinker paper (https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8135089/) and recreate the figures, all the while exploring the paper more and understanding single-cell RNA sequencing. At the end of the project, I will have knowledge about how to analyze and interpret single-cell RNA-seq data, how it's used in understanding cancer and drug development!

Table of Contents
===========
1. [The Key Scientific Question](https://github.com/priyalT/Kinker-/edit/main/README.md#the-key-scientific-question)
2. [Week 1 Memo](https://github.com/priyalT/Kinker-/edit/main/README.md#the-key-scientific-question)


The Key Scientific Question
===========================
Using available scRNA-seq data from cancer cell lines, how would you explore the use of the following FDA-approved antibody therapies in additional cancers?

Trastuzumab: Targets HER2 and is used in the treatment of HER2-positive breast and gastric cancers.

Bevacizumab: Targets VEGF and is used for a variety of cancers, including colorectal, lung, glioblastoma, breast, liver, and kidney cancer.

Week 1 Memo
============
I break down the KSQ into many parts, starting from the very first word that we encounter as we read it: scRNA-seq.

scRNA-seq
----------
Single cell technologies refer to technologies that take into account the heterogeneity of a tissue. Using next generation sequencing technologies, single-cell techniques examine the genetic information from each cell, providing a higher resolution of cellular differences and a better understanding of the function of an individual cell in the context of its microenvironment. scRNA-seq technology basically means RNA-sequencing technology for single cells (RNA-seq technology is the technology used to get transcriptome data, i.e data about the RNA sequence). One important application of the scRNA‐seq technology is to build a better and high‐resolution catalogue of cells in all living organism, commonly known as atlas, which is key resource to better understand and provide a solution in treating diseases. 

As time went on, the number of cells analysed increased from a hundred per experiment to a few hundred thousand per experiment. This was due to the drastic decrease in the cost of analysis of these. The procedures of scRNA‐seq mainly include single‐cell isolation and capture, cell lysis, reverse transcription (conversion of their RNA into cDNA), cDNA amplification and library preparation. Let's dive into the steps:

1. Single cell isolation and capture: It is the process of capturing high‐quality individual cells from a tissue, thereby getting precise biochemical and genetic information. The traiditional bulk sequencing methods fail to capture the heterogeneity of the cells of a tissue-they only capture total level of signals from a tissue. Depending on the organisms, tissues or cell properties, single cell isolation methods are largely different.



Cancer cell lines are just cell lines derived from cancerous cells. Cell lines are groups of cells growing and dividing indefinitely. They're made in the laboratory as models for experiments.
The KSQ or the Key Scientific Question talks about how we can use scRNA seq data of cancer cell lines to explore how the following FDA drugs can also be used for other cancers:
1. Trastuzumab targets HER2 and is used in the treatment of HER2-positive breast and gastric cancers. HER2 is an epidermal receptor protein which is overexpressed in cancerous states of the body, and remains underexpressed in normal states.
2. Bevacizumab targets VEGF which is a signaling protein, helps in the formation of new blood vessels and in vasodilation as well. If VEGF is overexpressed, it can lead to metstatic cancers. Solid cancers by themselves cannot metstasize, but if cancerous cells gain the ability to produce VEGF, they can easily form new blood vessels and be transported through blood and metastatize. Bevacizumab is used for a variety of cancers, including colorectal, lung, glioblastoma, breast, liver, and kidney cancer.
