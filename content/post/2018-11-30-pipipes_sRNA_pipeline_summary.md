## pipipes small-RNAseq pipeline

### 01 map to rRNA
filter reads mapping to rRNA, use -k 1 option for speed purpose

```
bowtie -r -S -v $rRNA_MM -k 1 -p $CPU \   ###rRNA_MM rRNA map mismatch allowed
		--un $x_rRNA_INSERT \
		rRNA \
		${input_reads}
```

### 02 map to hairpin
with $hairpin_MM mismatch(es) allowed; only keep unique mappers

```
bowtie -r --norc -v $hairpin_MM -m 1 --best --strata -p $CPU -S \   ###hairpin_MM mismatch
		--al $x_rRNA_HAIRPIN \                              ###hairpin mapped
		--un $x_rRNA_x_hairpin \                            ###rRNA & hairpin both unmapped
		hairpin \
		$x_rRNA_reads \                                     ###rRNA unmapped reads input;
		  | \

	samtools view -bSF 0x4 | \
	bedtools_piPipes bamtobed -i - > ${PREFIX}.x_rRNA.hairpin.v${hairpin_MM}m1.bed

	piPipes_insertBed_to_bed2 $x_rRNA_INSERT ${PREFIX}.x_rRNA.hairpin.v${hairpin_MM}m1.bed > $x_rRNA_HAIRPIN_BED2 && \
	rm -rf ${PREFIX}.x_rRNA.hairpin.v${hairpin_MM}m1.bed && \
	bed2lendis $x_rRNA_HAIRPIN_BED2 > $x_rRNA_HAIRPIN_BED2_LENDIS
```

### 03 genome mapping

```
	bowtie -r -v $genome_MM -a --best --strata -p $CPU \
		-S \
		genome \
		$x_rRNA_reads \                                     ###rRNA unmapped reads input
		2> $x_rRNA_GENOME_LOG | \
	samtools view -uS -F0x4 - 2>/dev/null | \
	bedtools_piPipes bamtobed -i - > ${PREFIX}.x_rRNA.hairpin.${GENOME}v${genome_MM}a.bed
	piPipes_insertBed_to_bed2 $INPUT ${INSERT%.insert}.${GENOME}v${genome_MM}a.insert.bed > ${GENOME_ALLMAP_BED2} && \
	rm -rf ${INSERT%.insert}.${GENOME}v${genome_MM}a.insert.bed
```
	Separating unique and multiple mappers
	bam file transformed to pipipes custom bed file ,and row 5 in bed were nnumber-of-hits

### 04 separate siRNA & piRNA by length (then plot length distribtion by R custom code)

```
	awk '$3-$2>=$siRNA_bot && $3-$2<=$siRNA_top' ${GENOME_ALLMAP_BED2} > ${GENOME_ALLMAP_BED2%bed2}siRNA.bed2
	awk '$3-$2>=$piRNA_bot && $3-$2<=$piRNA_top' ${GENOME_ALLMAP_BED2} > ${GENOME_ALLMAP_BED2%bed2}piRNA.bed2
```

### 05 map to piRNA cluster/transposon

```
	bowtie -r -v ${transposon_MM} -a --best --strata -p $CPU \
		-S \
		${t} \                                               ### transposon & cluster index
		${rRNA_remove_input} \
		2> ${TRN_OUTDIR}/${t}.log | \

	samtools view -uS -F0x4 - 2>/dev/null | \
	samtools sort -o -@ $CPU - foo | \
	bedtools_piPipes bamtobed -i - > $TRN_OUTDIR/${INSERT%.insert}.${t}.a${transposon_MM}.insert.bed
```

