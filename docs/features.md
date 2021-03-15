# Functional Features Prediction and Visualization Tutorial

The purpose of this tutorial is to demonstrate how to predict and visualizing transcripts using IsoTV. The following inputs will be used to visualize the *PDK2* gene: annotated transcriptome file (.gtf), transcript sequences (.fa/.fas), and isoform expression.

The data used for tutorial can be found in the [GitHub](https://github.molgen.mpg.de/MayerGroup/IsoTV) under `example/data`.

The goal is to reconstruct the figure for the *PDK2* gene from the IsoTV paper, which can also be found under `example/PDK2_tutorial.pdf`. It will assume that IsoTV has already been downloaded and installed.

## Configuration

To follow this tutorial, the `config_example_pdk2.yaml` configuration file can be used. However, the file needs to be modified to include the full local paths for the required prediction tools.

Input file directory:
```
| -- IsoTV
    | -- example/
        | -- data/
            | -- genes.tab
            | -- PDK2.nanopore.gtf
            | -- PDK2.transcriptome.fas
            | -- PDK2.counts.txt
    ...
```

Paths to be changed:
```
iupred2a_path: "/path/to/iupred2a/iupred2a.py"

brewery_path: "/path/to/Brewery/Brewery.py"

interproScan_path: "/path/to/my_interproscan/interproscan-5.38-76.0/interproscan.sh"

prositeScan_path: "/path/to/ps_scan/ps_scan.pl"
pfScan_path: "/path/to/ps_scan/pfscan"
prositeDat_path: "/path/to/prosite.dat"
```

## Executing

The command below can be used to run IsoTV for this tutorial. This command needs to be executed from the IsoTV directory itself.

```
snakemake -j 32 Results/Output/test.pdf --configfile config_example_pdk2.yaml
```

This will use the `config_example_pdk2.yaml` configuration file, run prediction analysis on *PDK2*, and create `test.pdf` under `example/Results/Output/test.pdf`

## Output

As the working directory has been set to `example`, all the intermediate, temporary, and output files will be created under `example`. The file that we are interested is `test.pdf`. Verify that this file is the same as `example/PDK2_tutorial.pdf`.    

Output file directory:
```
| -- IsoTV
    | -- example/
        | -- Results/
            | -- Genes/
                | -- PDK2/
                    | -- PDK2_functional_analysis.pdf
            | -- Plots/
                | -- PDK2_functional_analysis.pdf
            | -- Output/
                | -- test.pdf
    ...
```
