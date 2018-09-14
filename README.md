# Lineage-sequencing - proof-of-concept
This archive contains python notebook scripts for analysing 'Lineage sequencing'.

These scripts were used to analyse the data associated with the manuscript:
"Quantification of somatic mutation flow in individual cell division events 
by ‘lineage sequencing’"

## Overview:
Lineage sequencing is a new genome sequencing approach that assign mutation calls to specific events in developing clonal cell populations up to single-cell division resolution. Lineage sequencing utilizes knowledge of the cell lineage structure to reconstruct mutational events occurring during lineage formation with high resolution, accuracy, precision, and minimal bias. This scripts were used to analyse the two Lineages presented in the manuscript:
1. a human colon cancer cell line with a DNA polymerase epsilon (POLE) proofreading deficiency (HT115) and 
2. a human retinal epithelial cell line immortalized by constitutive telomerase expression (RPE1)).

### Running example code
The scrpits were written in Python 2.7 on Jupyter notebook. This scripts demonstrates step-by-step analysis of the data.
#### Step 1: 
##### Set_mutation_List.ipynb
We used Mutect1 as variant callers, which run for every pair of sub clones twice, such that each sample acted as a “tumor” sample in one run for a sub clone pair, and as a “normal” sample in another run of the same sub clone pair. This script combine the full SNV lists from all samples de-duplicate and prepare panda Dataframe of all the variants from each lineage. 

##### The ready dataframe from HT115 lineage: 'HT115_full_mutations.pkl'
##### and thr ready dataframe from RPE1 lineage: 'RPE1_full_mutations.pkl'


#### Step 2:


