# Translation

The translation step involves the translation of all transcripts for each gene from a nucleotide sequence to an amino acid sequence.

In order to translate a transcript, open reading frames were identified using start codon sequence *ATG* and scored using the Kozak Sequence position weight matrix. Potential upstream open reading frames were dismissed until the open reading frame located in the CDS was found. Every transcript for each input gene were translated into and stored in their own `fasta` files.  

## Usage

ONT Processing Input -
```
/path/to/input/genes/genes.tab
/Results/GffCompare/nanopore.combined.gtf
/Pinfish/corrected_transcriptome_polished_collapsed_tcons_nonredundant.fas
```

Gene input -
```
/path/to/input/genes/genes.tab
/path/to/gene_sequences.fas
```

Output - `/Genes/GENE/Transcripts/x.fa`

## Configuration

`gene_file: "/path/to/input/genes/genes.tab"` - The input file detailing for which genes the isoform analysis should be conducted for. One gene should be specified per line.


## Output Folder Structure

```
| -- Genes/
    | -- GENE/
        | -- GENE_transcripts_stats.txt
        | -- GENE_seq.fa
        | -- Transcripts/
            | -- x.fa
            ...
    ...
```
