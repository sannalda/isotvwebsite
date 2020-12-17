# Basecalling

## Usage

Input - `RawData/X.fastq`

Output - `Results/Pychopper/X.pychop.fastq`

`snakemake`

## Configuration

Below are changes that can be configured in the **config.yaml** file or explicitly specified in the command line.

### Guppy

`min_mean_q: 5` - Minimum read quality to keep.


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
