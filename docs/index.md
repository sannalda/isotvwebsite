# Introduction

IsoTV is Snakemake pipeline to analyze and visualize functional features of translated transcript isoforms. IsoTV incorporates various tools to predict protein domains, secondary structure, disordered regions, and post-translational modification sites. The visualization facilitates comparison of the set of transcript isoforms expressed across conditions and explored the functional consequences of isoform differences. IsoTV supports a range of transcriptome sequencing technologies, including short-reads, Oxford Nanopore (ONT) long-reads, Pacific Bio-sciences (PacBio) long-reads. It also supports other inputs, including single or multiple gene sequences.

There are three major components to this tool:

* Raw ONT Reads Processing - Assembling a *de novo* based transcriptome from raw ONT signals or basecalled ONT reads. Also, generates remapped files to the constructed transcriptome and quantifies individual isoform expression levels.
* Isoform Transcript Processing - Translating isoform transcripts from mRNA sequences to amino acid sequences.
* Translated Isoform Feature Analysis - Processing and visualizing functional features for each isoform.

This documentation provides a comprehensive overview of pipeline. Below describes the outline of the key topics discussed in the documentation:

* [Tools](tools.md) summarizes the external tools used for this pipeline.
* [Installation](prerequisite.md) discusses hows to install the pipeline as well as all the prerequisite tools needed.
* [Modules](overview.md) covers in depth of the various processes and tools within the pipeline.
* [Tutorial](general.md) describes about how to use the pipeline, as well snakemake basics and cluster computing capabilities.
