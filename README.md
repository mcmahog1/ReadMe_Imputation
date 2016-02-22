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

###*Question:*### How would the phasing algorithm use recombination rates.





