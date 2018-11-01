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

Additional analysis:

GO enrichment analysis:

+ clusterProfiler, [website](https://bioconductor.org/packages/release/bioc/html/clusterProfiler.html), [example](https://guangchuangyu.github.io/2016/01/go-analysis-using-clusterprofiler/)

Pathway Enrichment Analysis and Functional Annotation:

+ ReactomePA, [website](https://bioconductor.org/packages/release/bioc/html/ReactomePA.html), [Documentation](https://guangchuangyu.github.io/software/ReactomePA/documentation/), [example](http://www.pnas.org/content/113/20/5688)


### Reference

1. `RiboWave` - Ribosome elongating footprints denoised by wavelet transform comprehensively characterize dynamic cellular translation events

论文链接：[https://www.ncbi.nlm.nih.gov/pubmed/29945224](https://www.ncbi.nlm.nih.gov/pubmed/29945224)  

软件链接：[https://lulab.github.io/Ribowave](https://lulab.github.io/Ribowave)

> 清华大学生命学院鲁志课题组在《Nucleic Acids Research》杂志在线发表方法学论文题为《核糖体分析数据降噪处理及细胞翻译动态性特征的描述》（Ribosome elongating footprints denoised by wavelet transform comprehensively characterize dynamic cellular translation events）。该论文利用小波变换对核糖体分析（ribosome profiling, Ribo-seq）数据进行系统性降噪，开发了一套新型的鉴定RNA翻译活性的方法RiboWave。


2. Ribo-seq method

论文链接：[https://www.nature.com/articles/nprot.2012.086.pdf](https://www.nature.com/articles/nprot.2012.086.pdf)

> Recent studies highlight the importance of translational control in determining protein abundance, underscoring the value of
measuring gene expression at the level of translation. We present a protocol for genome-wide, quantitative analysis of in vivo
translation by deep sequencing. This ribosome profiling approach maps the exact positions of ribosomes on transcripts by nuclease
footprinting. The nuclease-protected mRNA fragments are converted into a DNA library suitable for deep sequencing using a
strategy that minimizes bias. The abundance of different footprint fragments in deep sequencing data reports on the amount of
translation of a gene. In addition, footprints reveal the exact regions of the transcriptome that are translated. To better define
translated reading frames, we describe an adaptation that reveals the sites of translation initiation by pretreating cells with
harringtonine to immobilize initiating ribosomes. The protocol we describe requires 57 days to generate a completed ribosome
profiling sequencing library. Sequencing and data analysis require a further 45 days

3. Computational resources for ribosome profiling: from database to Web server and software

[PDF file](http://159.226.118.232/open/upload/biology/papers/2018/201709-Brief_bioinfo-Computational_resources_for_ribosome_profiling.pdf)

> Ribosome profiling is emerging as a powerful technique that enables genome-wide investigation of in vivo translation at
sub-codon resolution. The increasing application of ribosome profiling in recent years has achieved remarkable progress toward
understanding the composition, regulation and mechanism of translation. This benefits from not only the awesome
power of ribosome profiling but also an extensive range of computational resources available for ribosome profiling. At present,
however, a comprehensive review on these resources is still lacking. Here, we survey the recent computational advances
guided by ribosome profiling, with a focus on databases, Web servers and software tools for storing, visualizing and
analyzing ribosome profiling data. This review is intended to provide experimental and computational biologists with a reference
to make appropriate choices among existing resources for the question at hand.

4. systemPipeR Workflow for Ribo-Seq and polyRiboSeq Experiments

[PDF file](https://bioconductor.org/packages/devel/bioc/vignettes/systemPipeR/inst/doc/systemPipeRIBOseq.pdf)



