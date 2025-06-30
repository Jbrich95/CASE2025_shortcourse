
## Instructions

First, download this repository and navigate to its top-level directory within the terminal.

### Software dependencies

Before installing the software dependencies, users may wish to setup a [conda](https://docs.conda.io/projects/conda/en/latest/user-guide/install/linux.html) environment, so that the dependencies of this repository do not affect the user's current installation. To create a conda environment, run the following command in terminal:

```
conda create -n CASE_env -c conda-forge r-base python=3.10.17
```

Then activate the conda environment with:

```
conda activate CASE_env
```

The above conda environment installs R and Python 3 automatically. Once both R and Python are setup, install the R package dependencies (given in `dependencies.txt`) by running the following command from the top-level of the repository:

```
Rscript dependencies_install.R; Rscript keras_check.R 
```
This will also install the Python dependencies, via the R package `reticulate`.

Note that Linux systems have several system dependencies that may need to be installed before installing `devtools` (e.g., `fontconfig1`, `harfbuzz`, and `fribidi`). If you run into problems when installing `devtools`, try installing it manually with  `conda` using the command (other R packages can also be installed this way):

```
conda install -c conda-forge r-devtools
```

or by manually installing the system dependencies before installing `devtools` manually in R:

```
sudo apt -y install libfontconfig1-dev libharfbuzz-dev libfribidi-dev
```

