---
title: "Yulab HiSeq"
date: 2018-10-23T16:34:40+08:00
draft: false

tags: ["hiseq"]
categories: ["biology"]

author: "Ming Wang"

# You can also close(false) or open(true) something for this content.
# P.S. comment can only be closed
comment: true
toc: true
autoCollapseToc: false
postMetaInFooter: false
hiddenFromHomePage: false
# You can also define another contentCopyright. e.g. contentCopyright: "This is another copyright."
contentCopyright: false
reward: false
mathjax: false
mathjaxEnableSingleDollar: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams: 
  enable: false
  options: ""

---

# Usage

leave a message here






## Ribo-seq

Analysis content:

![](http://159.226.118.232/open/upload/img/yulab_share_config/riboseq-analysis.png)

**part5 to part9**

+ 


+ Translation efficiency (part6)

The mRNA-seq and Ribo-seq data of four nematode species were retrieved from Stadler and Fire (2013). Genes with a normalized read count <1 in mRNA-seq were discarded to minimize the effect of inaccurate measurement of lowly expressed genes. The read count values in mRNA-seq (mRNA) and Ribo-seq (Ribo) were used to calculate ribosome density, which can infer translational initiation rate, also called translational efficiency (TE):

```math

TE = Ribo / mRNA

```

To compare translational efficiencies between orthologous genes, quantile normalization was performed on translational efficiencies among the four species.

> source: Genome Research, 2017 [url](https://genome.cshlp.org/content/27/9/1525)

+ Changes of translation efficiency (part7-9)

Results
We present a statistical framework and an analysis tool, RiboDiff, to detect genes with changes in translation efficiency across experimental treatments. RiboDiff uses generalized linear models to estimate the over-dispersion of RNA-Seq and ribosome profiling measurements separately, and performs a statistical test for differential translation efficiency using both mRNA abundance and ribosome occupancy.

Software: [RiboDiff](https://academic.oup.com/bioinformatics/article/33/1/139/2525694), Bioinformatics 2017

RiboDiff webpage [http://bioweb.me/ribodiff](http://bioweb.me/ribodiff)

Source code: [http://github.com/ratschlab/ribodiff](http://github.com/ratschlab/ribodiff)

+ Start coden prediction

Predict uORF in 5' UTR regions


+ ORF prefiction

The following identifies continuous ORFs in intergenic regions. Note, predORF can only identify continuous ORFs in query sequences.

See [RIBO-Seq Workflow](http://girke.bioinformatics.ucr.edu/systemPipeR/pages/mydoc/systemPipeRIBOseq.html)


In brief:

```
3 Read preprocessing
4 Alignments
5 Read distribution across genomic features
6 Adding custom features to workflow
7 Genomic read coverage along transripts or CDSs
8 Read quantification per annotation range
9 Analysis of differentially expressed genes with edgeR
10 GO term enrichment analysis of DEGs}
10.1 Obtain gene-to-GO mappings
10.2 Batch GO term enrichment analysis
11 Differential ribosome loading analysis (translational efficiency)
12 Clustering and heat maps
```
