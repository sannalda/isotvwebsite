# Visualization

The final NanoIso step is producing a visualization incorporating all of the functional analysis for each individual isoform. The report is generated for each gene, and if specified, also for the group of input genes. An example of the report is shown and explained below.

![Report](images/visualization_example.png "PDK2 Example")

* The first row contains the quantification of gene and transcription values. The first plot shows the total gene expression, the second plot shows individual isoform expression, and the third plot shows individual isoform usage.

* The second group visualizes the annotation for all transcripts. Each exon has also been uniquely annotated by NanoIso - If the exon from one transcript exactly matches the exon to another transcript, then they will classified the same. Note - Regardless of strand direction, every transcript is visualized left to right.

* The third group visualizes the various translational analysis. Each plot for each isoform has 8 different subparts.
    1. Mod Den - The density of modifications in that position.
    2. Mod - The identification of the 5 most common modifications.
    3. SS - Secondary structure.
    4. AA - Amino acid base.
    5. Exon - The position in the protein sequence that maps to the exons in the transcript sequence.
    6. Domain - Protein domains.
    7. Disorder - Score of  disorder, with 1 being highly disorder and 0 have low disorder.
    8. Prion - Score of probability of prion subsequence, with 1 being higher probability.  

* The fourth group contains the legend for the translation analysis plots in the previous group.

## Usage

Input -
```
/Genes/GENE/Transcripts/x_protein.fa
/Genes/GENE/Transcripts/x_protein.fa.ss3
/Genes/GENE/Transcripts/x_prion_score.txt
/Genes/GENE/Transcripts/x_protein_iupred2a.txt
/Genes/GENE/Transcripts/x_protein_sites.txt
/Genes/GENE/Transcripts/x_protein.gff3
```

Output - `/Genes/GENE/transcripts_filtered_coding_potential_analysis.pdf`

## Configuration

`output_plots: "test.pdf"` - An output file to create a pdf of all individual reports.

`output_seqs: "test/"` - An output folder to store the protein sequences for each transcript for each gene.

## Output Folder Structure

```
| -- Genes/
    | -- GENE/
        | -- GENE_protein_sequences.txt
        | -- GENE_transcripts_filtered_analysis.txt
        | -- Transcripts/
            | -- x_protein_analysis.txt
            ...
    ...
| -- test.pdf
| -- test/
    GENE_protein_sequences.txt
    ...
```
