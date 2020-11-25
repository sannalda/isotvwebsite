# Introduction

IsoTV is snakemake pipeline used to perform individual isoform transcription and translation analysis from RNAseq data, especially from Oxford Nanopore Technologies (ONT) long read datasets. It also has capabilities to process raw reads from ONTseq data.

There are three major components to this tool:

* Processing - Mapping and quantifying full length ONT reads to a *de novo* transcriptome.
* Analysis - Individual isoform transcriptional and functional analysis.
* Searching through the mollies and the weed

IsoTV is specifically geared towards processing and analyzing data across time (e.g. looking for isoform changes across two or more time points). However, it can be extrapolated to analyzing isoforms across conditions.

The [Tools](tools.md) summarizes the external tools used for this pipeline.
