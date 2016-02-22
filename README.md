# Practical: Imputation
# Objectives
1.Phase a set of subjects who have been directly genotyped

2.Impute phased haplotypes using the 1000 Genomes reference data

3.Carry out an association study on imputed data and interpret the results

#Log In

On a windows machine, press on the start button, type "Putty" into the search box.

In Putty enter the Host Name bluecrystalp3.acrc.bris.ac.uk and click open.

A new window will pop up, type in your username, press enter, and similiarly with your password.

The command line will now be visible that looks like: [username@newblue3 ~]$


Finallyy run the following command to access a compute node: qsub ‐I ‐q teaching ‐l
nodes=1:ppn=1, walltime=02:00:00


#Data
Data (directly genotyped data, genetic maps, reference halplotypes) for this practical is available in pract6_GWAS/data
Scripts (files containing commands) should be saved in pract3_GWAS/scripts
You should save your output to pract3_GWAS/output
If you get really stuck, example scripts and ready­made output are available
in pract3_GWAS/results (no peaking unless you have to!)


