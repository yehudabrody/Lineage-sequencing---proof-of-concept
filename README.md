# Lineage-sequencing - proof-of-concept
This archive contain python notebook scripts for analysing 'Lineage sequencing'.

These scripts were used to analyse the data associated with the manuscript:
"Quantification of somatic mutation flow in individual cell division events 
by ‘lineage sequencing’"

## Overview:
Lineage sequencing utilizes knowledge of the cell lineage structure to reconstruct mutational events occurring during lineage formation with high resolution, accuracy, precision, and minimal bias. This scripts were used to analyse the two Lineages presented in the manuscript:
1. HT115: a human colon cancer cell line with a DNA polymerase epsilon (POLE) proofreading deficiency
2. RPE1: a human retinal epithelial cell line immortalized by constitutive telomerase expression.

### Running example code
The scrpits were written in Python 2.7 on Jupyter notebook, and demonstrates step-by-step analysis of the data.
#### Step 1: 
##### Set_mutation_List.ipynb
We used Mutect1 as variant callers, which run for every pair of sub clones twice, such that each sample acted as a “tumor” sample in one run for a sub clone pair, and as a “normal” sample in another run of the same sub clone pair. This script combine the full SNV lists from all samples de-duplicate and prepare panda Dataframe of all the variants from each lineage. 

##### 'HT115_full_mutations.pkl': Ready dataframe, list of SNVs for HT115 lineage.
##### 'RPE1_full_mutations.pkl': and ready dataframe, list of SNVs for RPE1 lineage:


#### Step 2:
##### lineage_to_called variants_(active_search).ipynb


