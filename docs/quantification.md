# Quantification

The quantification step involves remapping and quantifying transcripts to the *de novo* transcriptome.

[Minimap2](https://github.com/lh3/minimap2) is first to map the reads to the transcriptome. Then, few custom scripts are used to normalize the reads using [DESeq2](https://bioconductor.org/packages/release/bioc/html/DESeq2.html) and calculate TPMs.

One thing to note here is that because Gffcompare filters redundant transcripts, there could be a potential loss of transcripts with alternative start and stop sites. As such, the mapping index was created from only non-redundant transcripts rather than filtering the transcripts after mapping.  

## Usage

Input - `Results/Gffcompare/nanopore.combined.gtf`

Output - `Results/Quantification/all_counts_deseq2norm_all.txt"`

`snakemake`

## Configuration

Below are changes that can be configured in the **config.yaml** file or explicitly specified in the command line.

### Minimap2

`minimap2_opts: -uf` - Required for stranded data.

`maximum_secondary: 200` - Output at most these many secondary alignments.

`secondary_score_ratio: 1` -  Minimum secondary to primary score ratio to output secondary mappings.

## Output Folder Structure

```
| -- IGV/
    | -- X.genome.bam
    | -- X.genome.bam.bai
    | -- X.transcriptome.bam
    | -- X.transcriptome.bam.bai
    ...
| -- Results/
    | -- Minimap2/
        | -- Transcriptome.mmi
    | -- Quantification/
        | -- X.bam
        | -- X.sorted.bam
        | -- X.sorted.bam.bai
        | -- X.counts
        ...
        | -- counts_all.txt
        | -- counts_deseq2norm_all.txt
```
