# Data folder

Open the `ImagingWorkshop2023.Rproj` file in `RStudio`.

Please run the `data_download.Rmd` script to obtain all data needed for the tutorials. 
When pressing the `knit` button in `RStudio` please make sure you select `Kint Directory` > `Project Directory` from the `knit` dropdown.

The following folders and associated data will be created within the `data` folder:

## steinbock

The `steinbock` folder contains the raw IMC data in MCD format in the `steinbock/raw` folder. This folder together with the `steinbock/panel.csv` file forms the basis for Session 2 to process multichannel images. Following Session 2 the `steinbock` framework will create the following folders within the `steinbock` folder:

* `img`: contains hot pixel filtered multi-channel images derived from the IMC raw data. One file per acquisition is generated.
* `images.csv`: contains metadata per acquisition.
* `masks_deepcell`: segmentation masks derived by deepcell segmentation.
* `intensities`: Contains one CSV file per acquisition. Each file contains single-cell measures of the mean pixel intensity per cell and channel based on the files in `img` and `masks_deepcell`.
* `regionprops`: Contains one CSV file per acquisition. Each file contains single-cell measures of the morphological features and location of cells based on `masks_deepcell`.
* `neighbors`: Contains one CSV file per acquisition. Each file contains an edge list of cell IDs indicating cells in close proximity based on `masks_deepcell`.

We will also obtain sample metadata in Excel format:

* `sample_metadata`: This file links each patient to their cancer type (SCCHN - head and neck cancer; BCC - breast cancer; NSCLC - lung cancer; CRC - colorectal cancer).

## gated_cells

This folder contains `SpatialExperiment` objects storing cells that were manually gated based on their expression values to derive ground truth cell phenotype labels. One file per cell phenotype and image was created.

## compensation

This folder holds one MCD file and multiple TXT files. Multiple spots of a "spillover slide" were acquired and each TXT file is named based on the spotted metal. This data is used for channel spillover correction. For more information, please refer to the original publication: [Compensation of Signal Spillover in Suspension and Imaging Mass Cytometry](https://www.cell.com/cell-systems/fulltext/S2405-4712(18)30063-2).