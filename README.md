# Multiplexed Tissue Imaging Workshop 2023

In this workshop we will demonstrate the main steps to perform computational analysis of highly multiplexed imaging data. 
The first day will start with a troubleshooting session to address possible issues when installing the required software. 
The first main session will highlight a number of interactive visualization approaches for imaging mass cytometry ([MCDViewer](https://www.standardbio.com/products-services/software)) and other highly multiplexed imaging data ([napari](https://napari.org/stable/), [QuPath](https://qupath.github.io/), [ImageJ/FIJI](https://imagej.net/software/fiji/)). 
Image processing and segmentation is performed using the steinbock framework ([https://github.com/BodenmillerGroup/steinbock](https://github.com/BodenmillerGroup/steinbock)). We will first give an overview of the framework prior to hands-on training. The final session of the first day will include an introduction to the [cytomapper](https://www.bioconductor.org/packages/release/bioc/html/cytomapper.html) and [imcRtools](https://bioconductor.org/packages/release/bioc/html/imcRtools.html) R/Bioconductor packages for reading spatially resolved, single-cell and multiplexed imaging data into R for analysis.

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

## Presentations and schedule

**11.01.2023**

| Time (CET)  | Topic                                                               |
| ----------- | ------------------------------------------------------------------- |
| 9.00h | Troubleshooting session |
| 10.00h | Welcome and coffee |
| 10.15h      | [Introduction](https://docs.google.com/presentation/d/1Jh4HZgL5eJyAF5Tx8C0KY7QS9pHkLyhzQ-g6uhtLMfQ/edit?usp=sharing) |
| 10.30h      | [Interactive visualization](https://docs.google.com/presentation/d/1IUnl2lz3iU_D_0grOAbYyBeVrPQDU1dI-RHlX0dt4ko/edit?usp=sharing)                           |
| 11.00h      | Hands-on training: interactive visualization                           |
| 11.30h      | Lunch                        |
| 12.30h      | [Image processing](https://docs.google.com/presentation/d/1465DGNcyM7nz7ffH-EQ1SVO0oSQm0kZcrkKjeauY-9M/edit?usp=sharing)  
| 13.00h      | Hands-on training: image processing         |
| 14.30h      | Coffee break   |
| 15.00h      | [Reading data into R and visualization](https://docs.google.com/presentation/d/1pOqtJfOQym8Hp6DbMGkZTGivP00zjiIXQ6Dw5mRQpuY/edit?usp=sharing) |
| 15.30h      | Hands-on training: reading data into R and visualization    |

**12.01.2023**

| Time (CET)  | Topic                                                               | 
| ----------- | ------------------------------------------------------------------- |
| 09.00h      | [Single-cell analysis](https://docs.google.com/presentation/d/1UnOzH7UWbO6hLywwIs5MoaCE75HxDglU9JBIAY4_a60/edit?usp=sharing)                                                             |
| 09.30h      | Coffee break          |
| 10.00h      | Hands-on training: single-cell analysis                                                       |
| 11.30h      | [Spatial data analysis](https://docs.google.com/presentation/d/1yqW_nMeW5ceQYBDCRTSssPRjaIhz7ghasD0yPd3w9pI/edit?usp=sharing)                         |
| 12.00h      | Lunch                                                    |
| 13.00h      | Hands-on training: spatial analysis                                                     |
| 14.30h      | Coffee break                                                     |
| 15.00h      | "Bring your own data"                                                     |

## Further resources

* [IMCDataAnalysis](https://bodenmillergroup.github.io/IMCDataAnalysis/) for a comprehensive overview on multiplexed image analysis.
* [steinbock](https://bodenmillergroup.github.io/steinbock/latest/) for image processing, segmentation and feature extraction.
* [imcRtools](https://bioconductor.org/packages/release/bioc/html/imcRtools.html) for spatial visualization and analysis.
* [cytomapper](https://bioconductor.org/packages/release/bioc/html/cytomapper.html) for image visualization and compensation.
* [Orchestrating single-cell analysis with Bioconductor](https://bioconductor.org/books/3.16/OSCA/) for an overview on single-cell analyses using Bioconductor packages.

