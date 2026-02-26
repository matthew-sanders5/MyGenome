# MyGenome

Quality control and trimming of paired-end Illumina reads for *Pyricularia pennisetigena* Pp371.

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Raw Data Acquisition](#raw-data-acquisition)
3. [Assess Sequence Quality](#assess-sequence-quality)
4. [Sequence Trimming](#sequence-trimming)
5. [Post-Trim Quality Assessment](#post-trim-quality-assessment)
6. [Read Statistics](#read-statistics)
7. [Directory Structure](#directory-structure)

---

## Project Overview

This repository documents quality assessment, trimming, and basic read statistics for paired-end Illumina sequencing data from *Pyricularia pennisetigena* strain Pp371. The goal is to generate a cleaned dataset suitable for downstream analyses (e.g., genome assembly) by identifying and mitigating common issues such as adapter contamination and end-of-read quality decay. All commands and parameters used are recorded to support reproducibility.

---

## Raw Data Acquisition

Will add pub level detail

---

## Assess Sequence Quality

This is a summary of the flags from the untrimmed sequences. This will be updated for publication polish, but documenting now.

```
Pp371_1.fq.gz
```
Orange Flags: Per tile sequence quality, Per base sequence content, Per sequence GC content
Red Flags: Overrepresented sequences, Adapter Content

```
Pp371_2.fq.gz
```
Orange Flags: Per tile sequence quality, Per sequence GC content, Overrepresented sequences
Red Flags: Per base sequence content, Adapter Content

---

## Sequence Trimming

Will add exact code for using the trimmer tool as described by manual

---

## Post-Trim Quality Assessment

This is a summary of the flags from the untrimmed sequences. This will be updated for publication polish, but documenting now.

```
Pp371_1_paired.fastq
```
Orange Flags: Per tile sequence quality, Per sequence GC content, Sequence Length Distribution
Red Flags: None

```
Pp371_2_paired.fastq
```
Orange Flags: Per tile sequence quality, Per sequence GC content, Sequence Length Distribution, Adapter Content
Red Flags: None

```
Pp371_1_unpaired.fastq
```
Orange Flags: Per tile sequence quality, Per sequence GC content, Sequence Length Distribution
Red Flags: None

```
Pp371_2_unpaired.fastq
```
Orange Flags: Per tile sequence quality, Per sequence GC content, Sequence Length Distribution
Red Flags:Per base sequence content, Adapter Content

---
