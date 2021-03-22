# Source

Below outlines the steps to install IsoTV, which requires `conda` to be installed as described in [prerequisites](prerequisite.md).

1. Download the **IsoTV** pipeline into a folder named `IsoTV`:

        git clone https://github.molgen.mpg.de/MayerGroup/IsoTV.git

2. Change the working directory into the new `isotv`:

        cd IsoTV

3. Install conda software dependencies with:

        conda env create --name isotv_env --file environment.yaml

4. Initialize the conda environment with:

        conda activate isotv_env

5. To deactivate the conda environment after use:

        conda deactivate
