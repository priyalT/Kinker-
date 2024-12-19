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

As time went on, the number of cells analysed increased from a hundred per experiment to a few hundred thousand per experiment. This was due to the drastic decrease in the cost of analysis of these. The procedures of scRNA‐seq mainly include single‐cell isolation and capture, cell lysis, reverse transcription (conversion of their RNA into cDNA), cDNA amplification and library preparation. 

![image](https://github.com/user-attachments/assets/d8543132-14ea-41a3-8a4a-f2ead46cc342)

While scRNA-seq technology is amazing, it comes with its own set of limitations. 
Traditional scRNA-seq focus on capturing mRNA via its polyA tail. This is to ensure that mRNAs are enriched whereas rRNAs are removed. This ensures a clearer genetic picture of expression. But, recently, scientists have realised that other types of RNA, like non-coding RNA and microRNAs are also important for controlling gene activity. They, however, do not have a polyA tail and are not picked up in the traditional scRNA-seq technology. 
1. This problem, to a certain extent, can be solved by small-seq which is a technique that is used to study small RNAs (less than 300 nucleotides long) like microRNAs and fragments of tRNAs. This method uses a combination of “oligonucleotide masks” (that inhibit the capture of highly abundant 5.8S rRNA molecules) and size selection to exclude large RNA species such as other highly abundant rRNA molecules.
2. Larger non-poly(A) RNAs like long non-coding RNA or circular RNA cannot be filtered by size because of highly abundant ribosomal RNA molecules. Single-cell RamDA-seq combats this problem by performing reverse transcription with random priming (random displacement amplification) in the presence of “not so random” (NSR) primers specifically designed to avoid priming on rRNA molecule. This way, the method captures more of the full-length RNA from the cell, including non-poly(A) RNAs, with less interference from rRNA.
3. This method, however, also has its drawbacks. The NSR primers were carefully designed according to rRNA sequences in the specific organism (mouse), and designing new primer sets for other species would take considerable effort.
4. CRISPR-based scDash has been recently used to remove rRNA sequences from single-cell total RNA-seq libraries.
5. Moreover, bacteria and prokaryotic species are currently not used for scRNA-seq technology because they lack poly(A) mRNAs. Thus, the development of single-cell RNA-seq methods that do not depend on poly(A) tail capture will also be instrumental in enabling single-cell resolution microbiome studies.

Cancer Cell Lines
------------------
Cancer is a group of diseases involving abnormal cell growth with the potential to invade or spread to other parts of the body. Cancer cells are cells that have lost the ability of contact inhibition, i.e, stopping division when cells come in contact with other cells. They continue to grow abnormally, competing with other cells for nutrition, and inevitably harming the body. They are also able to spread from one part of the body to another in a process known as metastasis. To study human cancer biology, researchers can use patient biopsies or tissue from the surgical resection of tumors. However, this tissue represents a single snapshot in the life history of that tumor, typically at an advanced stage. In order to investigate the dynamic genetic and epigenetic course of cancer initiation, progression and metastasis, experimental model systems are required. The most commonly used systems are cancer cell lines. Cell lines are groups of cells growing and dividing indefinitely. They're made in the laboratory as models for experiments. Cell lines have the advantage of being derived from patients and are more easily manipulated in the laboratory. They are immortalized. Cancer cells that keep dividing and growing over time, under certain conditions in a laboratory are cancer cell lines. Cancer cell lines are used in research to study the biology of cancer and to test cancer treatments. Human cancer-derived cell lines are fundamental models used in laboratories to study the biology of cancer, and to test the therapeutic efficacy of anticancer agents. HeLa was the first cultured cancer line. It was derived from cervical cancer cells taken from Henrietta Lacks in 1951.

Trastuzumab
------------
It is a FDA-approved drug which is sold under the name Herceptin. It is a monoclonal antibody, which is an antibody made by cloning a unique WBC from a cell lineage. It is used to treat gastric and breast cancers. Specifically, it is used for cancers that are HER2 Positive. Trastuzumab works by binding to HER2, a protein involved in cell growth found in large amounts on some cancer cells. This binding blocks the ability of HER2-positive cancer cells to send chemical signals that tell them to grow. It also stimulates the immune system to kill cells that have a lot of HER2.

Mechanism of action:

1. HER2 activates two important pathways:
	1.	PI3K/Akt pathway: Promotes cell survival and growth.
	2.	MAPK pathway: Promotes cell division and blood vessel growth (angiogenesis), which nourishes the tumor.
2. Trastuzumab binds to a specific part (Domain IV) of HER2 on the outside of the cancer cell and stops it from sending growth signals. It:
	1.	Stops HER2 signaling:
    
      	•	By binding to HER2, it blocks the signals that tell the cell to grow.
      
      
      	•	It also reduces AKT activation, which is part of the growth pathway.


	2.	Arrests cell division:

    
    	•	Trastuzumab stops cancer cells in the G1 phase of the cell cycle, preventing them from dividing and spreading.

   	
	3.	Activates tumor suppressors:

    
    	•	It increases levels of proteins like p27, which naturally slow down the cell cycle and stop cell division.

   	
	4.	Prevents angiogenesis:

    
    	•	It reduces the formation of new blood vessels, which tumors need to grow.

   	
	5.	Stops HER2 cleavage:

    
    	•	Sometimes, HER2’s extracellular part is cleaved (cut off), leaving the remaining part even more active. Trastuzumab blocks this cleavage.

   	
	6.	Immune response:

    
    	•	Trastuzumab helps recruit the immune system to attack cancer cells through a process called antibody-dependent cell-mediated cytotoxicity (ADCC). Immune cells are drawn to the 
        trastuzumab-coated cancer cells and destroy them.

HER2
----
Human epidermal growth factor receptor 2 or HER2 is a member of human epidermal growth factor receptor family. It is coded by the ERBB2 gene located at chromosome 17. 

1. ERBB: It consists of ERBB-1, ERBB-2, ERBB-3, ERBB-4. Each protein has three parts: extracellular ligand binding domain, a transmembrane domain, and an intracellular domain.


Bevacizumab
------------

VEGF
-----





KSQ in simpler terms
---------------------
The KSQ or the Key Scientific Question talks about how we can use scRNA seq data of cancer cell lines to explore how the following FDA drugs can also be used for other cancers:
1. Trastuzumab targets HER2 and is used in the treatment of HER2-positive breast and gastric cancers. HER2 is an epidermal receptor protein which is overexpressed in cancerous states of the body, and remains underexpressed in normal states.
2. Bevacizumab targets VEGF which is a signaling protein, helps in the formation of new blood vessels and in vasodilation as well. If VEGF is overexpressed, it can lead to metstatic cancers. Solid cancers by themselves cannot metstasize, but if cancerous cells gain the ability to produce VEGF, they can easily form new blood vessels and be transported through blood and metastatize. Bevacizumab is used for a variety of cancers, including colorectal, lung, glioblastoma, breast, liver, and kidney cancer.
