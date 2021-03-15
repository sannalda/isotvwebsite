# Functional Features Prediction and Visualization Tutorial

The purpose of this tutorial is to demonstrate how to predict and visualizing transcripts using IsoTV. The following inputs will be used to visualize the *PDK2* gene: annotated transcriptome file (.gtf), transcript sequences (.fa), and isoform expression.

The data used for tutorial can be found in the GitHub page under `example/data`.

The goal will be to construct the figure for the *PDK2* gene from the IsoTV paper, which is also under `example/PDK2_tutorial.pdf`.

## Configuration

To follow this tutorial, use the `config_example_pdk2.yaml` configuration can be used. However, this file needs to modify to include the full local paths for the required prediction tools (shown below). 

Input file directory:
```
| -- IsoTV
    | -- example/
        | -- data /
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

It will use the `config_example_pdk2.yaml` configuration file, run prediction analysis on *PDK2*, and create `test.pdf` under `example/Results/Output/test.pdf`

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
