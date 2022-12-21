# Multiplexed Tissue Imaging Workshop 2023

In this workshop we will demonstrate the main steps to perform computational analysis of highly multiplexed imaging data. 
The first day will start with a troubleshooting session to address possible issues when installing the required software. 
The first main session will highlight a number of interactive visualization approaches for imaging mass cytometry ([MCDViewer](https://www.standardbio.com/products-services/software)) and other highly multiplexed imaging data ([napari](https://napari.org/stable/), [QuPath](https://qupath.github.io/), [ImageJ/FIJI](https://imagej.net/software/fiji/)). 
Image processing and segmentation is performed using the steinbock framework [https://github.com/BodenmillerGroup/steinbock](https://github.com/BodenmillerGroup/steinbock). We will first give an overview of the framework prior to hands-on training. The final session of the first day will include an introduction to the [cytomapper](https://www.bioconductor.org/packages/release/bioc/html/cytomapper.html) and [imcRtools](https://bioconductor.org/packages/release/bioc/html/imcRtools.html) R/Bioconductor packages for reading spatially resolved, single-cell and multiplexed imaging data into R for analysis.

The second day will focus on analysis approaches presented in our online book for multiplexed image analysis ([https://bodenmillergroup.github.io/IMCDataAnalysis/](https://bodenmillergroup.github.io/IMCDataAnalysis/)). In the first session of the day we will present general single-cell analysis approaches including dimensionality reduction, visualization, clustering and cell type classification as well as channel-to-channel spillover correction and image visualization. The second session will demonstrate common spatial analysis approaches including spatial community detection, cellular neighborhood and spatial context analysis and cell type/cell type interaction testing. Finally, in the last session you can bring your own data and discuss open challenges with experts of the lab.

## Accessing the code

To access the code you can clone the current repository via

```
git clone https://github.com/BodenmillerGroup/ImagingWorkshop2023.git
```

or you can click the `Code` > `Download ZIP` button.

## Installation instructions

Please follow the instructions in the [Setup](Setup) folder on how to install the needed software.

## Data download

The `data_download.R` script in the [data](data) folder allows you to download all needed data.

## Follow along

Session 3-5 will be conducted in R. The R markdown scripts can be found in the individual folder. Please always ensure that you open the `ImagingWorkshop.Rproj` file before starting the session.

## Further resources
