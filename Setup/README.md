# Software setup

## Session 1

`napari` instructions

## Session 2

`steinbock` instructions

Alternative tools for interactive image visualization include the ([MCDViewer](https://www.standardbio.com/products-services/software)) specifically for imaging mass cytometry as well as [QuPath](https://qupath.github.io/) and [ImageJ/FIJI](https://imagej.net/software/fiji/)) for more general multiplexed image visualization.

## Session 3-5

To follow sessions 3 to 5 please have [R](https://stat.ethz.ch/CRAN/) and [RStudio](TODO) installed.
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