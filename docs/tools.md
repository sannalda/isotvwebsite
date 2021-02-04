# Tools used in IsoTV

IsoTV incorporates many external tools. Below are descriptions and references to all the tools that were used.

## ONT Reads Processing

* [Filtlong](https://github.com/rrwick/Filtlong/) - Filtering reads by their quality.
* [Pychopper](https://github.com/nanoporetech/pychopper) - Finding full length transcripts.
* [Pinfish](https://github.com/nanoporetech/pinfish) - Obtaining transcription using genome-based transcript polishing.
* [Gffcompare](https://github.com/gpertea/gffcompare) - Comparing obtained transcription to existing annotation.
* [Minimap2](https://github.com/lh3/minimap2) - Mapping reads to a *de novo* defined transcriptome.
* [DeSeq2](https://genomebiology.biomedcentral.com/articles/10.1186/s13059-014-0550-8) - Normalize isoform expression across samples. 

## Functional Feature Analysis

* [ScanProsite](https://prosite.expasy.org/scanprosite/) - Identify potential protein functional sites and motifs from the [PROSITE](https://prosite.expasy.org/) database.
* [InterProScan](https://github.com/ebi-pf-team/interproscan/wiki) - Command line version of InterPro, allowing to predict protein function using data gathered from many different resources. Used for [Pfam](https://pfam.xfam.org/) protein domain prediction.
* [Porter5](https://github.com/mircare/Porter5/) - Protein secondary structure prediction.
* [IUPred2A](https://iupred2a.elte.hu/) - Identify regions of disorder.
