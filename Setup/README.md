# Software setup

**Of Note:** Please join the troubleshooting session on the beginning of the first day if you experience issues installing the software.

## Session 1

`napari` instructions

Alternative tools for interactive image visualization include the ([MCDViewer](https://www.standardbio.com/products-services/software)) specifically for imaging mass cytometry as well as [QuPath](https://qupath.github.io/) and [ImageJ/FIJI](https://imagej.net/software/fiji/)) for more general multiplexed image visualization.

## Session 2

`steinbock` instructions

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
                       "bluster","scran", "lisaClust", "spicyR", "imcRtools", "cytomapper"))

# Github dependencies
if (!requireNamespace("devtools", quietly = TRUE))
    install.packages("devtools")

devtools::install_github("i-cyto/Rphenograph")
```