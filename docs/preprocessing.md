# Preprocessing

The preprocessing step involves searching for full length transcripts from raw basecalled reads.

First, basecalled ONT reads are filtered by the minimum read quality using [Filtlong](https://github.com/rrwick/Filtlong/). Then, full length transcripts are found using [Pychopper](https://github.com/nanoporetech/pychopper).

## Usage

Input - `RawData/X.fastq`

Output - `Results/Pychopper/X.pychop.fastq`

`snakemake`

## Configuration

Below are changes that can be configured in the **config.yaml** file or explicitly specified in the command line.

### Filtlong

`min_mean_q: 5` - Minimum read quality to keep.

### Pychopper

`porechop_heu_stringency: 0.25` - Stringency of porechop heuristic.

## Output Folder Structure

```
| -- FilteredData/
    | -- X.fastq
    ...
| -- Results/
    | -- Pychopper/
        | -- X.pychop.fastq
        ...
```
