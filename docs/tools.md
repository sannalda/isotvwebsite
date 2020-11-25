# External Tools

NanoIso uses and combines many external tools. Below are references and descriptions for all the tools used.

## Preprocessing

### Preprocessing
* [Filtlong](https://github.com/rrwick/Filtlong/) - Filtering reads by their quality.
* [Pychopper](https://github.com/nanoporetech/pychopper) - Finding full length transcripts.

### Transcriptome
* [Pinfish](https://github.com/nanoporetech/pinfish) - Obtaining transcription using genome-based transcript polishing.
* [Gffcompare](https://github.com/gpertea/gffcompare) - Comparing obtained transcription to existing annotation.

### Quantification
* [Minimap2](https://github.com/lh3/minimap2) - Mapping reads to a *de novo* defined transcriptome.

## Analysis

### Disorder
* [IUPred2A](https://iupred2a.elte.hu/) - Identify regions of disorder in proteins.

### Domain
* [InterProScan](https://github.com/ebi-pf-team/interproscan/wiki) - Command line version of InterPro, allowing to predict a protein's function using data gathered from many different resources.

### Structure
* [Porter5](https://github.com/mircare/Porter5/) - Protein secondary structure prediction.

### Phosphorylation Sites
* [ScanProsite](https://prosite.expasy.org/scanprosite/) - Scans for phosphorylation binding motifs.
