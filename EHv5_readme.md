# **ExpansionHunter v5 Pipeline:**

# **Overview:**

The goal of the Expansion Hunter pipeline is to estimate sizes of repeat expansions by performing a targeted search for reads using a whole-genome BAM/CRAM file. We call repeat expansions in PCR-free whole-genome sequencing data using ExpansionHunter v5 (https://github.com/Illumina/ExpansionHunter, PMID:28887402), which estimates the number of copies of repeated short unit sequence by performing a targeted search through a BAM/CRAM file for reads that span, flank, or are fully contained in each repeat. By combining evidence from multiple read signals, this approach is capable of genotyping repeats at a locus of interest even when the expanded repeat is substantially larger than the read length. For example, the method is capable of discovering and accurately estimating the size of C9Orf72 repeat expansions containing as many as \~1000 (\~6Kbp) copies of the motif. Our catalog currently covers disease-associated repeats located in the following genes: ABCD3, AFF2, AFF3, AR, ARX, ,ATN1, ATXN1, ATXN10, ATXN2, ATXN3, ATXN7, ATXN8OS, BEAN1, C9ORF72, CACNA1A, CBL, CNBP ,COMP, CSTB, DAB1, DIP2B, DMD, DMPK, EIF4A3 ,FGF14, FMR1, FRA10AC1, FOXL2, FXN, GIPC1, GLS, HOXA13, HOXD13, HTT, JPH3, LRP12, MARCHF6, NIPA1, NOP56, NOTCH2NL, NUTM2B\_AS1, PABPN1, PHOX2B, PPP2R2B, PRDM12, PRNP, RAPGEF2, RFC1, RILPL1, RUNX2, SAMD12, SOX3, STARD7, TBP, TBX1, TCF4, THAP11, TNRC6A, VWA1, XYLT1, YEATS2, ZFHX3, ZIC2, ZIC3, ZNF713. Information on these repeat expansions has been collated from public sources including PubMed, STRchive, STRanger, STRipy,and Gnomadv3.1.2 Pathogenic STR Browser, and are subject to change with advances in the field. Please see "Readme.Repeats.txt" for further information on the repeat loci, associated phenotypes, and information sources.

# **Pipeline Deliverables:**

1\. VCF FILES ({sample}.eh.vcf): The VCF file is formatted according to the ExpansionHunter specifications.

2\. Genotype Summary Table ({sample}.eh.summary\_table.annotated.txt): An annotated summary file that reports the ExpansionHunter genotype, status of the repeat, and additional characteristics for each locus. The columns in this file are:  
RepeatId: Name of the Repeat  
RepeatUnit: Sequence of the Repeat  
TargetRegion: Chromosomal Region  
Genotype: A pair of repeat sizes separated by / for diploid chromosomes and a single repeat size for haploid chromosomes  
GenotypeCi: Confidence interval for the size of each repeat allele  
Phenotype: Phenotype associated with the expanded repeat  
OMIM\_ID: OMIM ID for that phenotype/disease  
Classifications: Status Classification Categories  
Classification\_ranges: Repeat size ranges for each classification category  
Status: Repeat Status for the sample

3\. IF APPLICABLE: Project-level Repeat Locus Summary Table  ({Repeat\_locus}.summary\_table.txt): Project-level summary files, 1 for each assessed locus. The columns in this file are:  
SampleId: Id of the Sample  
RepeatUnit: Sequence of the Repeat  
TargetRegion: Chromosomal Region  
Genotype:  A pair of repeat sizes separated by "/" for diploid chromosomes and a single repeat size for haploid chromosomes  
GenotypeCi: Confidence interval for the size of each repeat allele  
Phenotype: Phenotype associated with the expanded repeat  
OMIM\_ID: OMIM ID for that phenotype/disease  
Classifications: Status Classification Categories  
Classification\_ranges: Repeat size ranges for each classification category  
Status: Repeat Status for the sample