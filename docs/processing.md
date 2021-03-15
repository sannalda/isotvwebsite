# ONT Processing Tutorial

The data used for tutorial is taken from the SG-NEx (Signapore Nanopore Expression) Project, and more information can be found here: [SG-NEx](https://github.com/GoekeLab/sg-nex-data).

## Input

The working directory should be setup in the configuration file:
`outdir:/path/to/output`. This directory will be used for data input and output.

Below is the the input file structure for `.fastq` files, and how it should be in the configuration file.

Input file structure:

```
| -- RawData/Fastq/
    | -- A549_r1_r3.fastq
    | -- A549_r2_r1.fastq
    | -- A549_r5_r3.fastq
    ...
```

Configuration file structure:
```
samples:
    A549_1: "A549_r1_r3"
    A549_2: "A549_r2_r1"
    A549_5: "A549_r5_r3"
    ...
```

## Configuration Settings

Outside of the changing the external tool paths, here are some additional configuration settings to keep in mind of.

```
### General pipeline parameters:
basecalling: FALSE
preprocess: TRUE
annotation: TRUE
quantification: TRUE
```

Also, create a line-delimited file with a list of genes of interest. For the sake of example, can just create a file with the gene `ABI2`.

```
gene_file: "/home/annaldas/projects/isoform_analysis/genes.tab"
output_plots: "test.pdf"
```

## Command

```
snakemake --snakefile /path/to/isotv/snakemake -j 32
```
