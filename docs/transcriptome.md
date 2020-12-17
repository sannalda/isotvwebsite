# Building a De Novo Transcriptome

The transcriptome step involves constructing a *de novo* based transcriptome from the full length transcripts.

[Minimap2](https://github.com/lh3/minimap2) is first used to construct an initial mapping to the reference genome. Then, [Pinfish](https://github.com/nanoporetech/pinfish) is used to polish the genome-based transcript to obtain the transcriptome. This is done by first clustering reads with similar intron and exon structure,

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

### Minimap2

`minimap2_opts_junction: TRUE` - Use annotation to improve splice junction mapping.

`minimap2_opts: -uf` - Required for stranded data.

`minimum_mapping_quality: 5` - Minimum mapping quality.

`minimap2_opts_polished: -s` - Required for stranded data.

### Pinfish

`spliced_bam2gff: 0.25` - Stringency of porechop heuristic.

`minimum_cluster_size: 3` - Minimum size to cluster transcripts.

`exon_boundary_tolerance: 10` - Exon boundary tolerance.

`terminal_exon_boundary_tolerance: 50` - Terminal exon boundary tolerance.

`minimum_isoform_percent: 1` - Minimum percentage of reads necessary to call an isoform.

`collapse_internal_tol: 5` - Internal exon boundary tolerance.

`collapse_five_tol: 500` - 5' boundary tolerance.

`collapse_three_tol: 50` - 3' boundary tolerance.

`spliced_bam2gff_opts_pol: -s` - Required for stranded data.


## Output Folder Structure

```
| -- ReferenceData/
    | -- junctions.bed
| -- Results/
    | -- Minimap2/
        | -- ReferenceFasta.mmi
        | -- merged.mapping.bam
    | -- Pinfish/
        | -- raw_transcripts.gff
        | -- clustered_pol_transcripts.pol_gff
        | -- cluster_memberships.tsv
        | -- clustered_transcripts_collapsed.gff
        | -- polished_transcripts.fas
        | -- polished_reads_aln_sorted.bam
        | -- polished_transcripts.gff
        | -- polished_transcripts_collapsed.gff
        ...
```
