# nnCSR2D

## Description

This is a simple NN surrogate model, intended to simulate coherent synchrotron radiation (CSR) in the final
bend of the FACET-II bunch compressor. The root folder contains the primary jupyter notebook CSR2D Torch Current.ipynb,
as well as two older versions for reference, and the data partitions and weights from various dates. The data partitions
are txts (should be updated to jsons soon), and, assuming the ordering of the files in the source directory is not changed,
indicate the indices in the data array populated by load_data corresponding to training, validation, and test data.

The raw data consists of a series of simulation outputs from JuliaCSR2D (https://github.com/weiyuanlou/JuliaCSR2D). These
are h5 files containing a sequence of wakefields and beam densities, stored as 2d arrays, as well as geometric scale 
parameters, at each step s of the tracking. 

The model consists of a CNN block, which takes in a 256x128 image representing the 2D beam density on a fixed grid, as well as
3 scalar paremters  (simulation step s, horizontal scale factor dx, longitudinal scale factor dz) and proceeds to extract and 
compress the features. The final compressed feature array is then flattened into a 1D array, to which scalar parameter data are 
appended before passage through a dense NN and upsampling into another CNN, with produces the 2x256x128 grids representing the
predicted wakefield density.

### Dependencies

pytorch 2.2.2  
numpy 1.26.3  
A GPU is assumed to be available for training; you can try modifying the code to run without one but it will be a very 
slow process.  

### Executing program

The notebook should be executed sequentially, with appropriate changes to the file paths.

## Authors

Obed Camacho  
River Robles
