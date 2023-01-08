# Image processing

This document contains the instructions used in *Section 2: Image processing*.

Please make sure you have cloned/downloaded an up-to-date version of this repository, completed the [setup instructions](../Setup/README.md) and [downloaded the data](../data/README.md).

For questions or help, please employ the *steinbock* `--help` option (after step 2), consult the [workshop slides](https://docs.google.com/presentation/d/1465DGNcyM7nz7ffH-EQ1SVO0oSQm0kZcrkKjeauY-9M/edit?usp=sharing) or the [steinbock documentation](https://bodenmillergroup.github.io/steinbock/), or raise your hand.


## 1. Preparing the data

*SSH participants: skip this step*

### Windows

    cd C:\path\to\ImagingWorkshop2023\data
    mkdir steinbock-new
    xcopy steinbock\raw steinbock-new\raw

In above command, adapt `C:\path\to\ImagingWorkshop2023\data\steinbock-new` as needed.

### Mac OS/Linux

    cd /path/to/ImagingWorkshop2023/data
    mkdir steinbock-new
    cp -r steinbock/raw steinbock-new/raw

In above command, adapt `/path/to/ImagingWorkshop2023/data/steinbock-new` as needed.


## 2. Configuring steinbock

### Windows

Define a `steinbock` macro:

    doskey steinbock=docker run -v "C:\path\to\ImagingWorkshop2023\data\steinbock-new":/data ghcr.io/bodenmillergroup/steinbock:0.15.0 $*
    steinbock --version

In above command, adapt `C:\path\to\ImagingWorkshop2023\data\steinbock-new` as needed.

Verify that the final output reads `steinbock, version 0.15.0`.

### Mac OS / Linux / SSH

Define a `steinbock` alias:

    alias steinbock="docker run -v "/path/to/ImagingWorkshop2023/data/steinbock-new":/data -u $(id -u):$(id -g) ghcr.io/bodenmillergroup/steinbock:0.15.0"
    steinbock --version

In above command, adapt `/path/to/ImagingWorkshop2023/data/steinbock-new` as needed.

Verify that the final output reads `steinbock, version 0.15.0`.


## 3. Configuring channels

*SSH participants: skip this step*

Infer a *steinbock* panel file from raw IMC data:

    steinbock preprocess imc panel --unzip

Inspect the generated `panel.csv` file.

Overwrite it with the provided one.


## 4. Pre-processing raw IMC data

Extract and pre-process IMC acquisitions:

    steinbock preprocess imc images --unzip --hpf 50

Inspect the generated multi-channel images in the `img` directory, e.g. using ImageJ/Fiji or napari.


## 5. Segmenting cells using DeepCell/Mesmer

Perform Mesmer whole-cell segmentation:

    steinbock segment deepcell --app mesmer --minmax

Inspect the generated cell masks in the `masks` directory, e.g. using ImageJ/Fiji or napari.


## 6. Measuring cell intensities

Aggregate pixel intensities per cell & marker:

    steinbock measure intensities --aggr mean

Inspect the generated single-cell data in the `intensities` directory.


## 7. Measuring cell morphology

Measure morphological properties per cell:

    steinbock measure regionprops

Inspect the generated single-cell data in the `regionprops` directory.


## 8. Finding cell neighbors

Identify cells in spatial proximity:

    steinbock measure neighbors --type expansion --dmax 4

Inspect the generated cell pair lists in the `neighbors` directory.


## 9. Exporting data to other file formats

*These steps are optional and given without further explanations.*

Images:

    steinbock export ome
    steinbock export histocat

Single-cell data (intensities, morphology):

    steinbock export csv intensities regionprops -o cells.csv
    steinbock export fcs --no-concat intensities regionprops -o fcs
    steinbock export anndata --no-concat --intensities intensities --data regionprops --neighbors neighbors -o anndata

Cell neighbors (spatial cell graphs, open using e.g. [CytoScape](https://cytoscape.org) or [gephi](https://gephi.org)):

    steinbock export graphs --format graphml --data intensities
