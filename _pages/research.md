---
layout: archive
title: "Research interests"
permalink: /research/
author_profile: true
---

# Current research actitivies and interests
- Analyzing single-cell transcriptomic data from 30 human brain studies and implementing computational methods to identify disease-relevant cell types
- Comparing 11 computational methods to prioritize cell types relevant to diseases/traits from GWAS variants and scRNAseq data
- Maintaining and developing the front-end and back-end of FUMA, a web-platform used to functionally annotate summary statistics from genome-wide association studies
- Mapping GWAS variants to genes using multi-omics quantitative trait loci 

# Summary of activities at Xbiome
- Developing a bioinformatics pipeline to identify tumor neoantigens from paired tumor-normal WES data from cancer patients
- Developing a bioinformatics pipeline to map tumor neoantigens to the patient's microbiome
- Applying pipelines that I developed to analyze cancer dataset to study neoantigen diversity, crosslink bacterial antigen diversity and association to immunotherapy responses

# Summay of activities at Ambry Genetics
- Processed NGS data from raw *bcl* files to *fastq* files using bcl2fastq and performed quality control of the sequencing data based on mean coverage, number of bases with different amount of coverage, or percent perfect barcode matching
- Provided bioinformatics expertise and support to wetlab scientists to troubleshoot failed sequencing runs such as analyzing contamination, on target rate, or DNA fragment sizes
- Gained knowledge and experience in NGS sequencing from different Illumina machines such as Hiseq, Nextseq, and Novaseq and Roche’s assay for ctDNA
- Acquired knowledge and experience in sequencing for confirmation of copy number variation such as Sanger sequencing or MLPA
- Developed a bioinformatics pipeline to identify somatic variants and germline variants from paired tumor-normal whole exome sequence data and from tumor-only whole exome sequence data
- Developed a bioinformatics pipeline to process RNA-seq data from raw BCL file to gene counts

# Post-doc research
My post-doc research focuses on using NGS data (whole genome, whole exome, and RNA-seq) to understand human health and disease

## X-inactivation
![image](https://user-images.githubusercontent.com/10180091/146855168-66a16bf2-862f-48d1-b3d8-25714369233e.png)
- Preprint is here: https://www.biorxiv.org/content/10.1101/785105v2.abstract
- Abstract: One of the X chromosomes in genetic females is silenced by a process called X chromosome inactivation (XCI). Variation in XCI across the placenta may contribute to observed sex differences and variability in pregnancy outcomes. However, XCI has predominantly been studied in human adult tissues. Here we sequenced and analyzed DNA and RNA from two locations from 30 full-term pregnancies. Implementing an allele specific approach to examine XCI, we report evidence that XCI in the human placenta is patchy, with large patches of either silenced maternal or paternal X chromosomes. Further, using similar measurements, we show that this is in contrast to adult tissues, which generally exhibit mosaic X-inactivation, where bulk samples exhibit both maternal and paternal X chromosome expression. Further, by comparing skewed samples in placenta and adult tissues, we identify genes that are uniquely silenced or expressed in the placenta compared to adult tissues highlighting the need for tissue-specific maps of XCI.

## Neoepitope prediction
![image](https://user-images.githubusercontent.com/10180091/146855294-e7bfe2f8-e122-470f-914b-0c7b527bd7d1.png)
- Publications:
  + https://www.nature.com/articles/s41598-021-90170-1
  + https://www.nature.com/articles/s41598-020-68939-7

## Variant calling on the sex chromosome
- chrX and chrY are homologous at the pseudoautosomal regions (PARs)
- Consequence: when mapping an XX sample to a default reference genome (includes both chrX and chrY), chrX reads mismap to chrY 
![image](https://user-images.githubusercontent.com/10180091/147518972-5f7d4b24-a120-45a2-9243-850e06c6c490.png)
- Solution: use a sex-complement reference genome 
  + Webster et al. 2019 GigaScience (I was an author on this)
  + If sample is XX:
    + Use a reference genome with the Y masked out
  + If sample is XY:
    + Use the reference genome with the PARs on the Y masked out
- Method:
  + Map samples to a Default reference or a Sex-Complement reference
- Observation:
  + Number of variants genotyped on chrX is increased
![image](https://user-images.githubusercontent.com/10180091/147519057-72495fda-9b3e-424e-8254-af5ca9098abb.png)
- Developing best practices for variant calling on the sex chromosomes:
  + Mapping: Map to a Sex-Complement reference
  + Genotyping:
    + Joint-call within females and within males
    + Male on chrX: haploid
    + GATK default is diploid, which results in heterozygous sites at homologous regions with chrX

# PhD Research
My research during my PhD centers around leveraging the availability of large-scale genomic data to develop methods and models for the analysis of genetic variation across species. 

## Natural selection
Does natural selection reduces variation at sites that are putatively neutral? Population geneticists have postulated that neutral sites could also be affected by natural selection if they are linked to those directly under selection, via genetic hitchhiking or background selection. Even though genetic diversity (DNA differences within species) at neutral sites has been shown to be reduced by linked selection, whether linked selection has also affected divergence (DNA differences between species) was still debated. I utilized genome-wide divergence data between species with different split times (i.e. human-chimp and human-mouse) to show that natural selection has also reduced divergence at linked neutral sites. I also developed a likelihood method to model different evolutionary forces, particularly linked selection, mutagenic recombination, and biased gene conversion in shaping patterns of divergence across the genome. 

Published work: Phung, T.N., Huber, C.D., and Lohmueller, K.E. (2016). Determining the Effect of Natural Selection on Linked Neutral Divergence across Species. PLOS Genet 12, e1006199.

## Sex-biased demography
Comparing and constrating the genetic diversity between the X chromosome and the autosomes is a tool to study whether any evolutionary process has been sex-biased and has been fruitful in providing insights into human evolutionary history. Recently, studying the genetics and the evolutionary history of dogs has captured the fascination of both scientists and the public alike. Despite documented sex-biased mating practices in both wild and domestic population of canines, current studies have not investigated whether any evolutionary process has been sex-biased. I used whole-genome sequence data from multiple populations of dogs and wolves to test whether the demography of canines has been sex-biased. 

Published work: Phung, T.N., Wayne, R.K., Sayres, M.A.W., and Lohmueller, K.E. (2018). Complex patterns of sex-biased demography in canines. Proceedings of the Royal Society B 286 (1903), 20181976.

## Genetic architecture
Understanding the genetic architecture of complex traits is key to unravel the genetic basis of complex traits. I leverage summary statistics from genome-wide association studies (GWAS) to develop a method to infer the mutational target size for each complex trait. I also study the extent to which selection is coupled with the variant's effect on the trait. 
