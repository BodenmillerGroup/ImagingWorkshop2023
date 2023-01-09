# Image visualization

This document contains some instructions used in Section 1: Interactive image visualization.

Please make sure you have cloned/downloaded an up-to-date version of this repository, completed the setup instructions and downloaded the data.

For questions or help, please consult the [workshop slides](https://docs.google.com/presentation/d/1IUnl2lz3iU_D_0grOAbYyBeVrPQDU1dI-RHlX0dt4ko/edit?usp=sharing) or raise your hand.

## IMC raw data inspection using napari-imc

Extract the file `Patient/Patient4.mcd` from the archive `Patient4.zip` in `ImagingWorkshop2023/data/steinbock/raw` to a known location.

Launch napari using the command prompt (Windows) or the terminal (Mac OS, Linux):

    conda activate napari
    napari

In napari, click `File -> Open File(s)...` and open the file `Patient4.mcd`.

Instructions on how to use napari-imc are given in the workshop.


## Using napari from within Python / Jupyter Lab

Launch Jupyter Lab within the `ImagingWorkshop2023` directory using the command prompt (Windows) or the terminal (Mac OS, Linux):

    cd /path/to/ImagingWorkshop2023  # adapt as needed
    conda activate napari
    jupyter-lab
    
In Jupyter Lab, open the notebook `Session1_image_visualization/napari.ipynb`.

Instructions on how to use the notebook are given in the workshop.
