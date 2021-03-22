# Secondary Structure

An additional method to understand the functional effects of transcripts is to analyze protein secondary structure.

[Brewery](https://github.com/mircare/Brewery/) was used to predict secondary structure in 3 classes: alpha helix, beta sheets, and the rest.

NOTE: Secondary structure analysis can take a long time. Unless absolutely necessary, we recommend to turn this feature off during analysis.

## Usage

Input - `/Genes/GENE/Transcripts/x_protein.fa`

Output - `/Genes/GENE/Transcripts/x_protein.fa.ss3`


## Output Folder Structure

```
| -- Genes/
    | -- GENE/
        | -- Transcripts/
            | -- x_protein.fa.ss3
            ...
```
