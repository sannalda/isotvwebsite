# Tutorial Introduction

This tutorial is a guide for the general usage for the pipeline. Both the ONT Processing and the Isoform Visualization will be shown.

The data used for this tutorial is taken from the SG-NEx (Signapore Nanopore-Expression) Project, and more information can be found here: [SG-NEx](https://github.com/GoekeLab/sg-nex-data).

The given `config.yaml` has been configured a bit to handle this dataset.

To produce the visualization, run the following command once the configuration file has been set up:

```
snakemake --snakefile /path/to/isotv/snakemake -j 32 Results/Output/test.pdf
```

The rest of the tutorial will be updated as soon as possible!
