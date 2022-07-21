# IBECourse2022_SequencingData
Hands on session on how to generate and deal with sequencing data in bioinformatic analyses.
# VCF files and bcftools
*Materials created by Jose Serradell and Nerea Moreno.*

In this practical we will be analysing human sequencing data in the form of a multisample VCF, for this you will have to install bcftools in your command line and download the sample file and its index (https://github.com/nmorenoruiz21/IBECourse2022_SequencingData). 

Make sure to locate both files in your working directory:

- Sample file: samples.vcf.gz
- Index file: samples.vcf.gz.tbi

*Warning: without the corresponding index file, we will not be able to properly work with the samples*


## 1. Exploring the data

Save the file name in a bash variable so you don't have to type it every single time:
```
samp=samples.vcf.gz
```

Traverse the VCF and see how many individuals we are dealing with and what is the name of the samples:
```
less -S $samp
```

## 2. Filtering and Extracting data from VCFs

**Question 1.** How many *missense* variants are there?

```
# Type your answer here
```

**Question 2.** How many variants have a *dbSNP ID*?

* Option 1
```
# Type your answer here
```

* Option 2
```
# Type your answer here
```


**Question 3.** How many *C>T* changes are there?

```
# Type your answer here
```

**Question 4.** How many variants have a *CADD score* higher than 15?

```
# Type your answer here
```

**Question 5.** How many *missense* variants have a *CADD score* higher than 15?

```
# Type your answer here
```

**Question 6.** How many *A>G intronic* variants are there in *chromosome 1*?

```
# Type your answer here
```

**Question 7.** How many *missense homozygous* variants are there in *chromosome 19* in *sample 2*?

```
# Type your answer here
```

**Question 8.** How many *SNVs* are there?

```
# Type your answer here
```

**Question 9.** How many *homozygous indels* are there in *sample 1*?

```
# Type your answer here
```

**Question 10.** How many variants of *MODERATE* and *HIGH* impact are there in sample 1? (Meaning the total number of variants in sample 1 that are either MODERATE or HIGH)

```
# Type your answer here
```

**Question 11.** Imagine we are working at a hospital and are analysing patient genomes for medical purposes. Variants in the Long Intergenic non Protein Coding RNA 960 (LINC00960) are linked to poorer cancer prognosis through aggravated malignant behaviour in cancer cells. Imagine that the MD asks for you to report variants present in LINC00960 in order to decide further treatment of the patient. You have to prepare an Excel file for the physician with the most crucial variant information (coordinates, etc.)
```
# Type your answer here
```


**Question 12.** Now you are looking at a family, you have information on the proband (S1) and the mother (S2) and father(S3). S1 suffers from a recessive mendelian disorder. The MD asks for an Excel report in which he can easily see the crucial variant information, followed by the genotypes for the three individuals, the CADD score and the annotation in all variants with a functional effect that is HIGH or MODERATE. 
```
# Type your answer here
```

**Plots** You can plot simple statistics about the variation in the samples with a builtin bcftools command
```
bcftools stats -s S1,S2,S3 samples.vcf.gz > stats.vchk
plot-vcfstats -p plot_stats stats.vchk
```
