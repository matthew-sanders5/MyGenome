# MyGenome

Quality control, trimming, and de novo genome assembly of paired-end Illumina reads for *Pyricularia pennisetigena* Pp371.

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Raw Data Acquisition](#raw-data-acquisition)
3. [Assess Sequence Quality](#assess-sequence-quality)
4. [Sequence Trimming](#sequence-trimming)
5. [Post-Trim Quality Assessment](#post-trim-quality-assessment)
6. [Read Statistics](#read-statistics)
7. [Genome Assembly Strategy](#genome-assembly-strategy)
8. [K-mer Selection and Optimization](#k-mer-selection-and-optimization)
9. [Velvet Assembly (Round 1)](#velvet-assembly-round-1)
10. [Velvet Assembly (Round 2 Optimization)](#velvet-assembly-round-2-optimization)
11. [SPAdes Assembly](#spades-assembly)
12. [Assembly Metrics Comparison](#assembly-metrics-comparison)
13. [Assembly Graph Visualization (Bandage)](#assembly-graph-visualization-bandage)
14. [Directory Structure](#directory-structure)

---

## Project Overview

This repository documents quality assessment, trimming, and genome assembly of paired-end Illumina sequencing data from *Pyricularia pennisetigena* strain Pp371. The goal is to generate a cleaned dataset suitable for de novo genome assembly and evaluate assembly quality using multiple tools and metrics (genome size, contig count, N50, and graph structure).

---

## Raw Data Acquisition

Will add pub level detail

---

## Assess Sequence Quality

Raw paired-end reads were evaluated using FastQC prior to trimming. All warning (orange) and error (red) flags are summarized below.

---

<details>
<summary><strong>Pp371_1.fq.gz (Raw Forward Reads)</strong></summary>

```
Pp371_1.fq.gz
```

**Warning (Orange) Flags**
- Per tile sequence quality  
- Per base sequence content  
- Per sequence GC content  

**Error (Red) Flags**
- Overrepresented sequences  
- Adapter Content  

### Summary Tab

![FastQC Sequence 1 summary before trimming](images/sequence_1_raw_summary.jpg)

### Adapter Content Tab

![FastQC Sequence 1 adapter content before trimming](images/sequence_1_raw_adaptercontent.jpg)

</details>

---

<details>
<summary><strong>Pp371_2.fq.gz (Raw Reverse Reads)</strong></summary>

```
Pp371_2.fq.gz
```

**Warning (Orange) Flags**
- Per tile sequence quality  
- Per sequence GC content  
- Overrepresented sequences  

**Error (Red) Flags**
- Per base sequence content  
- Adapter Content  

### Summary Tab

![FastQC Sequence 2 summary before trimming](images/sequence_2_raw_summary.jpg)

### Adapter Content Tab

![FastQC Sequence 2 adapter content before trimming](images/sequence_2_raw_adaptercontent.jpg)

</details>

---

## Sequence Trimming

Reads were trimmed using Trimmomatic in paired-end mode.

```
java -jar trimmomatic.jar PE \
-phred33 \
Pp371_1.fq.gz Pp371_2.fq.gz \
Pp371_1_paired.fastq Pp371_1_unpaired.fastq \
Pp371_2_paired.fastq Pp371_2_unpaired.fastq \
ILLUMINACLIP:adaptors.fa:2:30:10 \
SLIDINGWINDOW:20:20 MINLEN:125
```

---

## Post-Trim Quality Assessment

This is a summary of the flags from the untrimmed sequences. This will be updated for publication polish, but documenting now.

```
Pp371_1_paired.fastq
```
Warning (Orange) Flags: Per tile sequence quality, Per sequence GC content, Sequence Length Distribution

Error (Red) Flags: None

Summary:

![FastQC Sequence 1 summary before trimming](images/sequence_1_pairedtrim_summary.jpg)

Adapter Content:

![FastQC Sequence 1 summary before trimming](images/sequence_1_pairedtrim_adaptercontent.jpg)

```
Pp371_2_paired.fastq
```
Waring (Orange) Flags: Per tile sequence quality, Per sequence GC content, Sequence Length Distribution, Adapter Content

Error (Red) Flags: None

Summary:

![FastQC Sequence 1 summary before trimming](images/sequence_2_pairedtrim_summary.jpg)

Adapter Content:

![FastQC Sequence 1 summary before trimming](images/sequence_2_pairedtrim_adaptercontent.jpg)

```
Pp371_1_unpaired.fastq
```
Warning (Orange) Flags: Per tile sequence quality, Per sequence GC content, Sequence Length Distribution

Error (Red) Flags: None

Summary:

![FastQC Sequence 1 summary before trimming](images/sequence_1_unpairedtrim_summary.jpg)

Adapter Content:

![FastQC Sequence 1 summary before trimming](images/sequence_1_unpairedtrim_adaptercontent.jpg)

```
Pp371_2_unpaired.fastq
```
Warning (Orange) Flags: Per tile sequence quality, Per sequence GC content, Sequence Length Distribution

Error (Red) Flags:Per base sequence content, Adapter Content

Summary:

![FastQC Sequence 1 summary before trimming](images/sequence_2_unpairedtrim_summary.jpg)

Adapter Content:

![FastQC Sequence 1 summary before trimming](images/sequence_2_unpairedtrim_adaptercontent.jpg)

---

## Genome Assembly Strategy

---

## K-mer Selection and Optimization

---

## Velvet Assembly (Round 1)

---

## Velvet Assembly (Round 2 Optimization)

---

## SPAdes Assembly

---

## Assembly Metrics Comparison

---

## Assembly Graph Visualization (Bandage)

---

## Directory Structure

---
