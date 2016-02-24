# Practical: Imputation
# Objectives
1.Phase a set of subjects who have been directly genotyped

2.Impute phased haplotypes using the 1000 Genomes reference data

3.Carry out an association study on imputed data and interpret the results

#Log In

On a windows machine, press on the start button and type "Putty" into the search box.

In Putty enter the Host Name "bluecrystalp3.acrc.bris.ac.uk" and click open.

A new window will pop up, type in your username, press enter, and similarly with your password.

The command line will now be visible which looks like: [username@newblue3 ~]$


Finally, run the following command to access a compute node: qsub ‐I ‐q teaching ‐l
nodes=1:ppn=1, walltime=02:00:00


#Data
Data (directly genotyped data, genetic maps, reference halplotypes) for this practical is available in pract6_GWAS/data.

We will be using the ‘clean’ GWAS dataset that you encountered in "Practical 3 : Genome­wide association
study in Plink".

We will be examining the transmembrane protein 18 (TMEM18) gene on the p telomere of chromosome 2 (2p25.3).

Scripts (files containing commands) can be found in pract6_GWAS/scripts

You can save your output to pract6_GWAS/output

We will not have enough time to phase and impute the data. If the program is taking to long and you are ready to move one, please press "control" and "z" together. This will stop the program and then refer to the ready­made output is available in pract6_GWAS/results.


#Exercise 1 ­ phasing the first 5 megabases (mB) of chromosome 2

Take a look at the genetic map file (e.g. head -n 10 data/geneticMap/)

###*Question 1:*

######How would the phasing algorithm use recombination rates (develop)?

###*Question 2:*

######How many subjects and SNPs are in the sample data? How many SNPs?


Navigate to the scripts folder (cd scripts).

Run the script phase.sh


#Exercise 2 ­ Impute haplotypes using the 1000 Genomes reference data 

Navigate to the scripts folder (cd scripts).

Take a look at the script impute.sh.

###*Question 3:*

######What do the following options mean with respect to the imputation process?

######-use_prephased_g

######-known_haps_g

######-m

######-l

######-h

######-int


Take a look at the reference haplotype and legend file.

zcat ../data/haplotypes/ALL.chr2.integrated_phase1_v3.20101123.snps_indels_svs.genotypes.nomono.haplotypes.gz | head -n 10
zcat ../data/legend/ALL.chr2.integrated_phase1_v3.20101123.snps_indels_svs.genotypes.nomono.legend.gz | head -n 10

###*Question 4:*
 
######What do the the runs of 0's and 1's represent in the haplotype file?


Run the script impute.sh

#Exercise 3 ­ run an association analysis on the imputed results 

#Answer to questions
###*Answer 1:*
The phasing algorithm can use recombination rates to help estimate the probable relationship between haplotypes (develop).


###*Answer 2:*
add plink as a module - "module add apps/plink-1.07"

obtain the path of the samples to be phased by taking a look the "phase.sh" script

run plink with no output - plink --bfile ../data/directlyGenotypedData/geno_qc_TMEM18 --noweb

There are 651 SNPs and 8,237 samples


###*Answer 3:*
-use_prephased_g - this implements imputation using genetic data that has already been phased into two haplotypes per person

-m - the indicates the genetic map which contains recombination rates

-l - this indicates the legend file which contains positions and alleles for the markers in the reference data

-h - this indicates the reference data haplotypes

-int - this gives the region currently to be imputed


###*Answer 4:*

These 0's represent allele 0 in the legend file and the 1's represent allele 1. Each sucessive pair of digits in each row represent a pair of genotypes (either 00, 01, 11) for one subject in the reference panel.  
