# Lineage-sequencing - proof-of-concept
This archive contains python notebook scripts for analysing 'Lineage sequencing'.

These scripts were used to analyse the data associated with the manuscript:
"Quantification of somatic mutation flow in individual cell division events 
by ‘lineage sequencing’"

## Overview:
Lineage sequencing utilizes knowledge of the cell lineage structure to reconstruct mutational events occurring during lineage formation with high resolution, accuracy, precision, and minimal bias. These scripts were used to analyse the two lineages presented in the manuscript:
1. HT115: a human colon cancer cell line with a DNA polymerase epsilon (POLE) proofreading deficiency
2. RPE1: a human retinal epithelial cell line immortalized by constitutive telomerase expression.
The original bam files (hg19) can be found at: https://www.ncbi.nlm.nih.gov/sra/SRP159787

### Running example code
The scripts were written in Python 2.7 on Jupyter notebook, and demonstrate step-by-step analysis of the data.
#### Step 1: 
##### Set_mutation_List.ipynb
We used Mutect1 as a variant caller, which ran for every pair of sub clones twice, such that each sample acted as a “tumor” sample in one run for a sub clone pair, and as a “normal” sample in another run of the same sub clone pair. This script combines the full SNV lists from all samples, removes duplicates, and prepares a pandas Dataframe of all the variants from each lineage. 

##### 'HT115_full_mutations.pkl': Ready dataframe, list of SNVs for HT115 lineage.
##### 'RPE1_full_mutations.pkl': Ready dataframe, list of SNVs for RPE1 lineage:


#### Step 2:
##### lineage_to_called variants_(active_search).ipynb
In the “optical tracking -> lineage -> called variants” approach, the lineage structure was determined by analysis of time lapse imaging of cells in the microfluidic trap array device. This lineage structure was subsequently used for calling branch variants. SNVs were grouped as coincident SNVs and branch variants called by evaluating the coincident SNV quality score for the highest scoring group of sub clones over all the groups of sub clones consistent with the lineage structure determined by time lapse imaging, including the option that an SNV is only truly present in a single sub clone and represents a leaf variant. 

Coincident SNV Quality Score = (MAX P clusters (Min P sample (P1/(P1+P2))).



#### Step 3:
##### Raw variants_to_Lineage_to_called variants.ipynb
In the “raw variants -> lineage -> called variants” approach, we used the shotgun sequence data to estimate the most likely lineage structure in each lineage experiment. This was accomplished by identifying coincident SNVs by analysis of raw SNV calls. Sub clones sharing the same SNVs were grouped without restrictions by hierarchical clustering and for each coincident SNV, the quality score was calculated as before:

Coincident SNV Quality Score = (Min P samples (P1/(P1+P2)))
