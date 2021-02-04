# Configuration

IsoTV has two configuration files - `environment.yaml`, which handles the necessary packages and dependences for the [conda environment](prerequisite.md), and `config.yaml`, which covers the general and specific pipeline parameters and paths. The overview to set up `config.yaml` is described below.

## Pipeline Configuration

The pipeline configuration is split into three parts: *general*, *processing*, *analysis*, and *tools*. There are file paths for files and tools that need to be set before running. Specific module specific configuration is discussed in [Modules](overview.md).

The below configuration ids can be configured in the **config.yaml** file or explicitly specified in the command line.

### General

`outdir:/path/to/output` - Path to output directory

`basecalling: FALSE` - Boolean to decide whether reads should be basecalled.
`preprocess: TRUE` - Boolean to decide whether to use the generated files from `processing` for isoform analysis or not. Refers specifically to the `nanopore_gtf`, `polished_reads`, and `counts_data` configuration for the *Analysis*.
`annotation: TRUE` - Boolean stating to use annotation file.
`quantification: TRUE` - Boolean to use quantification (isoform expression) file.

### ONT long read processing

```
guppy: "/path/to/Guppy324/bin/guppy_basecaller"
flowcell: FLO-MIN106
kit: SQK-DCS109
```
- Path to Guppy basecaller, and the information regarding the ONT flowcell and kit number.

```
genome_fasta: "/path/to/GRCh38.p12.primary_assembly.genome.fa"
genome_annot: "/path/to/gencode.v32.primary_assembly.annotation.gtf"
```
- Path to human genome primary assembly FASTA and GTF file. Recommendation is to use GRCh38.p12 and Gencode v32 respectively.

```
samples:
  A549_1: "A549_r1_r3"
  A549_2: "A549_r2_r1"
  ...
```
- Mapping of sample fasta filename to desired name. Sample name with `.fastq` extension. For reference, the notation `dayX_Y:"Z"` corresponds of the *X* day and *Y* replicate from the fastq file *Z* of the experiment. This notation is **required**.  

### Feature Analysis

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
- Path to the normalized transcript counts data. Required if not using NanoIso processing.
- **NOTE:** The transcript ids should match with the transcript ids from the `nanopore_gtf` and `polished_reads` file.

```
continuous: FALSE
```
- Boolean to let pipeline know if data is continuous or not.

### External tool paths

```
aa: TRUE
```
- Boolean if amino acid sequence should be visualized.

```
iupred2a: TRUE
iupred2a: "/path/to/iupred2a/iupred2a.py"
```
- Boolean if disorder regions should be predicted and visualized.
- Path to IUPred2A python file script.

```
porter: TRUE
brewery_path: "/path/to/Brewery/Brewery.py"
```
- Boolean if secondary structure should be predicted and visualized.
- Path to Porter5 python file script.

```
pfScan: TRUE
prositeScan_path: "/path/to/ps_scan/ps_scan.pl"
pfScan_path: "/path/to/ps_scan/pfscan"
prositeDat_path: "/path/to/prosite.dat"
```
- Boolean if post-translational modifications should be predicted and visualized
- Path to the Prosite scan perl file script and folder, and Prosite database.

```
java: "/pkg/openjdk-11.0.3.2-0/profile"
```
- Path to java. Only necessary if local Java is not at least version 11.
