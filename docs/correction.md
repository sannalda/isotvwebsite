# Correcting Isoform Reads

The transcriptome step involves correcting isoform reads from the *de novo* based transcriptome.

[Gffcompare](https://github.com/gpertea/gffcompare) is used to compare transcripts to the existing annotation to determine any potential redundant reads.

This part of the pipeline is primarly based on the **ont_tutorial_pinfish** released by Nanopore Technologies.  

## Usage

Input -
```
/path/to/genome/fasta/X.fa
Results/Pychopper/X.pychop.fastq
```

Output - `Results/Gffcompare/nanopore.combined.gtf`

`snakemake`

## Configuration

Below are changes that can be configured in the **config.yaml** file or explicitly specified in the command line.

### Gffcompare


## Output Folder Structure

```
| -- Results/
    | -- Pinfish/
        | -- corrected_transcriptome_polished_collapsed.fas
        | -- corrected_transcriptome_polished_collapsed_nonred.fas
    | -- Gffcompare/
        | -- nanopore.combined.gtf
        ...
```
