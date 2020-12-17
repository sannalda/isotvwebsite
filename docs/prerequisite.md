# Prerequisites

All software requirements for the *Raw ONT Reads Processing* are managed and stored in a `conda` environment. However for *Isoform Transcript Processing* and *Translated Isoform Feature Analysis*, these tools need to be installed locally by the user. Even though IsoTV is a python-based pipeline, some of these external tools are only available for Linux based operating systems and are respectively marked below.


## Installing Conda

Install `conda` as described at [https://conda.io/docs/install/quick.html](https://docs.conda.io/en/latest/miniconda.html)
```
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh
```

See [Source](source.md) on how to install and activate the environment.

**Note:** Newer versions of `conda` may have have package conflicts errors when trying to activate the environment. If this is the case, try downgrading the conda version to `4.6.14`.
```
conda install conda=4.6.14
```

## Installing External Tools

### IUPred2A

Install IUPred2A as described at [https://iupred2a.elte.hu/download_new](https://iupred2a.elte.hu/download_new)

### InterProScan 5

Install InterProScan as described at [https://github.com/ebi-pf-team/interproscan/wiki/HowToDownload](https://github.com/ebi-pf-team/interproscan/wiki/HowToDownload).

```
mkdir my_interproscan
cd my_interproscan
wget ftp://ftp.ebi.ac.uk/pub/software/unix/iprscan/5/5.46-81.0/interproscan-5.46-81.0-64-bit.tar.gz
wget ftp://ftp.ebi.ac.uk/pub/software/unix/iprscan/5/5.46-81.0/interproscan-5.46-81.0-64-bit.tar.gz.md5

md5sum -c interproscan-5.46-81.0-64-bit.tar.gz.md5

tar -pxzf interproscan-5.46-81.0-64-bit.tar.gz
```

**Note: Involves additional requirements (e.g. PANTHER)**.

```
cd data
wget ftp://ftp.ebi.ac.uk/pub/software/unix/iprscan/5/data/panther-data-14.1.tar.gz
wget ftp://ftp.ebi.ac.uk/pub/software/unix/iprscan/5/data/panther-data-14.1.tar.gz.md5

md5sum -c panther-data-14.1.tar.gz.md5

tar -pxvzf panther-data-14.1.tar.gz
```

### Porter5

Install Porter5 as described at [https://github.com/mircare/Porter5/](https://github.com/mircare/Porter5/).

```
git clone https://github.com/mircare/Porter5/ --depth 1 && rm -rf Porter5/.git
```

**Note: Involves additional requirements (e.g. HHblits, UniRef90). HHblits should already be part of** `environment.yaml`**.**
```
wget http://wwwuser.gwdg.de/~compbiol/data/hhsuite/databases/hhsuite_dbs/old-releases/uniprot20_2016_02.tgz
tar zxvf uniprot20_2016_02.tgz
```

### Prosite Scan

Install Prosite Scan from [ftp://ftp.expasy.org/databases/prosite/ps_scan/](ftp://ftp.expasy.org/databases/prosite/ps_scan/).
```
wget ftp://ftp.expasy.org/databases/prosite/ps_scan/ps_scan_linux_x86_elf.tar.gz
wget ftp://ftp.expasy.org/databases/prosite/prosite.dat
```
