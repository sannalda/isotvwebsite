# Configuration

IsoTV has two configuration files - `environment.yaml`, which handles the necessary packages and dependences for the [conda environment](prerequisite.md), and `config.yaml`, which covers the general and specific pipeline parameters and paths.

## Pipeline Configuration

The pipeline configuration is split into three parts: *general*, *processing*, *analysis*, and *tools*. There are file paths for files and tools that need to be set before running. Specific module specific configuration is discussed in [Modules](overview.md).

The below configuration ids can be configured in the **config.yaml** file or explicitly specified in the command line.

### General

`preprocess: TRUE` - Boolean to decide whether to use the generated files from `processing` for isoform analysis or not. Refers specifically to the `nanopore_gtf`, `polished_reads`, and `counts_data` configuration for the *Analysis*.

### Processing

```
genome_fasta: "/path/to/GRCh38.p12.primary_assembly.genome.fa"
```
- Path to human genome primary assembly FASTA file. Recommendation is to use GRCh38.p12.

```
genome_annot: "/path/to/gencode.v32.primary_assembly.annotation.gtf"
```
- Path to human genome primary assembly annotation GTF file. Recommendation is to use Gencode v32.

```
minimap2
```
- Minimap2 file path ((((NEEED TO BE DOUBLE CHECKED !!!!))))

```
samples:
  day5_1: "OJ32"
  day0_1: "OJ33"
  ...
```
- Mapping of sample fasta filename to desired name. Sample name with `.fastq` extension. For reference, the notation `dayX_Y:"Z"` corresponds of the *X* day and *Y* replicate from the fastq file *Z* of the experiment. This notation is **required**.  

### Analysis

```
gene_file: "/path/to/genes.tab"
```
- Input gene file to determine which genes to analyze. Genes are separated by a new line.

```
output_plots: "test.pdf"
```
- Output report filename to store the visualizations from all the genes required.

```
nanopore_gtf: "/path/to/nanopore.gtf"
```
- Path to gtf transcript file that was mapped to the *de novo* transcriptome. Required if not using NanoIso processing.
- **NOTE:** The transcript ids should match with the transcript ids from the `polished_reads` and `counts_data` files.

```
polished_reads: "/path/to/corrected_transcriptome.fa"
```
- Path to reads with polished sequences. Required if not using NanoIso processing.
- **NOTE:** The transcript ids should match with the transcript ids from the `nanopore_gtf` and `counts_data` file.

```
counts_data: "/path/to/counts.txt"
```
- Path to the normalized transcript counts data. Required if no using NanoIso processing.
- **NOTE:** The transcript ids should match with the transcript ids from the `nanopore_gtf` and `polished_reads` file.

### Tools

```
java: "/pkg/openjdk-11.0.3.2-0/profile"
```
- Path to java. Only necessary if local Java is not at least version 11.

```
iupred2a: "/path/to/iupred2a/iupred2a.py"
```
- Path to IUPred2A python file script.

```
porter: "/path/to/Brewery/Brewery.py"
```
- Path to Porter5 python file script.

```
prosite_scan: "/path/to/ps_scan/ps_scan.pl"
```
- Path to the prosite scan perl file script.

```
prosite_dat: "/path/to/prosite.dat"
```
- Path to the prosite database.
