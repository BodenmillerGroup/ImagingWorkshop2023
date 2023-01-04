# Software setup

**Of Note:** Please join the troubleshooting session on the beginning of the first day if you experience issues installing the software.

## Session 1

In session 1, we introduce several alternatives for viewing multi-channel images. Among these alternatives, we present the [napari](https://napari.org) image viewer for Python and the [napari-imc](https://github.com/BodenmillerGroup/napari-imc) plugin. In the workshop, we use [conda](https://docs.conda.io/) environments for installing both napari and napari-imc as follows:

1. [Install Miniconda](https://conda.io/projects/conda/en/stable/user-guide/install/index.html).

2. Open a [Command Prompt (Windows)](https://www.wikihow.com/Open-the-Command-Prompt-in-Windows) or Terminal ([Mac OS](https://support.apple.com/guide/terminal/open-or-quit-terminal-apd5265185d-f365-44cb-8b09-71a064a42125/mac#:~:text=Terminal%20for%20me-,Open%20Terminal,%2C%20then%20double%2Dclick%20Terminal.), Linux).

3. Execute the following commands:

    conda create -c conda-forge -n napari -y python=3.10
    conda activate napari
    pip install jupyterlab "napari[all]" napari-imc tifffile pandas

4. Execute ``jupyter-lab`` and verify that jupyter-lab opens.

5. Execute ``napari`` and verify that napari opens.

If you experience troubles installing Anaconda or running jupyter-lab/napari, please join the Troubleshooting Session on the first day of the workshop.

Other tools for interactive image visualization introduced during the workshop include the ([MCDViewer](https://www.standardbio.com/products-services/software)) specifically for imaging mass cytometry as well as [QuPath](https://qupath.github.io/) and [ImageJ/FIJI](https://imagej.net/software/fiji/)) for more general multiplexed image visualization.

## Session 2

In session 2, we use the [steinbock](https://github.com/BodenmillerGroup/steinbock) toolkit for multi-channel image processing. To be able to use the steinbock Docker container, please install [Docker Desktop](https://docs.docker.com/get-docker/) (Mac OS, Windows) or [Docker Server/Engine](https://docs.docker.com/engine/install/#server) (Linux). Depending on your operating system, additional configuration steps may be necessary as outlined below.

**Running steinbock on Apple M1 systems**: Unfortunately, the steinbock Docker container does not support Apple M1 systems at this point. If you want to follow the workshop using an Apple M1 system, we recommend to run steinbock on a Linux virtual machine instead. Please do not hesitate to [get in touch](mailto:jonas.windhager@uzh.ch) prior to the workshop in this case.

After installing and configuring Docker Desktop or Docker Server/Engine (see below), ensure that you can successfully run the steinbock Docker container:

1. Open a [Command Prompt (Windows)](https://www.wikihow.com/Open-the-Command-Prompt-in-Windows) or Terminal ([Mac OS](https://support.apple.com/guide/terminal/open-or-quit-terminal-apd5265185d-f365-44cb-8b09-71a064a42125/mac#:~:text=Terminal%20for%20me-,Open%20Terminal,%2C%20then%20double%2Dclick%20Terminal.), Linux).

2. Execute ``docker run ghcr.io/bodenmillergroup/steinbock --version``.

3. Verify that the output reads ``steinbock, version 0.15.0``.

If you experience troubles installing/configuring Docker or running the steinbock Docker container, please join the Troubleshooting Session on the first day of the workshop.

### Configuring Docker Desktop for Mac

Increase the memory that Docker Desktop is allowed to use as described [here](https://docs.docker.com/desktop/settings/mac/#advanced) (Docker Preferences --> Resources --> Advanced --> Memory). To avoid problems during the workshop, we recommend to set this to roughly 80% of the maximum available system memory.

### Configuring Docker Desktop for Windows

Make sure to NOT skip step 5 of the interactive installation instructions (adding your user to the *docker-users* group, if necessary).

Docker Desktop can run in either *Hyper-V mode* or in *WSL 2 mode*. To check/choose in which mode Docker Desktop is running, refer to the preferences menu as described [here](https://docs.docker.com/desktop/settings/windows/#general) (Docker Preferences --> General --> Use the WSL 2 based engine). In general, we recommend to run Docker Desktop in *WSL 2 mode* (i.e., with the "Use the WSL 2 based engine" checkbox ticked).

If and only if Docker Desktop is running in *Hyper-V mode* (i.e., with the "Use the WSL 2 based engine" checkbox grayed out or NOT ticked), increase the memory that Docker Desktop is allowed to use as described [here](https://docs.docker.com/desktop/settings/windows/#advanced) (Docker Preferences --> Resources --> Advanced --> Memory). To avoid problems during the workshop, we recommend to set this to roughly 80% of the maximum available system memory.

### Configuring Docker Server/Engine for Linux

To be able to run ``docker`` as non-root user, follow the [Docker Engine post-installation steps](https://docs.docker.com/engine/install/linux-postinstall/#manage-docker-as-a-non-root-user).


## Session 3-5

To follow sessions 3 to 5 please have [R](https://stat.ethz.ch/CRAN/) (version 4.2) and [RStudio](https://posit.co/download/rstudio-desktop/) installed.

Please be aware that Bioconductor does not support the Apple M1 (a.k.a. arm64) architecture in native mode yet, only via Rosetta, which is the emulator built into macOS Big Sur that enables Mac M1 systems to run Intel x86_64 apps. Concretely this means that if you are on an Apple M1 system, we strongly recommend that you use the official Intel 64-bit R (x86_64 arch) from CRAN available here: https://cran.r-project.org/bin/macosx/ (choose R-4.2.2.pkg, NOT R-4.2.2-arm64.pkg). This will run on the Apple M1 platform in emulation mode. (Taken from [https://support.bioconductor.org/p/9137290/#9137342](https://support.bioconductor.org/p/9137290/#9137342))

To install all needed software packages, open `RStudio` and execute the following code:

```
if (!requireNamespace("BiocManager", quietly = TRUE))
    install.packages("BiocManager")

BiocManager::install(c("pheatmap", "viridis",
                       "zoo", "devtools", "tiff",
                       "distill", "openxlsx", "ggrepel", "patchwork", "mclust",
                       "RColorBrewer", "uwot", "Rtsne", "cowplot", "kohonen", "caret", 
                       "randomForest", "ggridges", "cowplot", "gridGraphics",
                       "scales", "CATALYST", "scuttle", "scater", 
                       "dittoSeq", "tidyverse", "batchelor", 
                       "bluster","scran", "lisaClust", "spicyR", "imcRtools", 
                       "cytomapper", "imcdatasets"))

# Github dependencies
if (!requireNamespace("devtools", quietly = TRUE))
    install.packages("devtools")

devtools::install_github("i-cyto/Rphenograph")
```

Test the installation by executing the following code chunk in R:

```
library(pheatmap)
library(viridis)
library(zoo)
library(devtools)
library(tiff)
library(distill)
library(openxlsx)
library(ggrepel)
library(patchwork)
library(mclust)
library(RColorBrewer)
library(uwot)
library(Rtsne)
library(cowplot)
library(kohonen)
library(caret)
library(randomForest)
library(ggridges)
library(cowplot)
library(gridGraphics)
library(scales)
library(CATALYST)
library(scuttle)
library(scater)
library(dittoSeq)
library(tidyverse)
library(batchelor)
library(bluster)
library(scran)
library(lisaClust)
library(spicyR)
library(imcRtools)
library(cytomapper)
library(imcdatasets)
library(Rphenograph)
```