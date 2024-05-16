# Project Title

nnCSR2D

## Description

This is a simple CNN surrogate model, intended to simulate coherent synchrotron radiation (CSR) in the final
bend of the FACET-II bunch compressor. The root folder contains the primary jupyter notebook CSR2D Torch Current.ipynb,
as well as two older versions for reference, and the data partitions and weights from various dates. The data partitions
are txts (should be updated to jsons soon), and, assuming the ordering of the files in the source directory is not changed,
indicate the indices in the data array populated by load_data corresponding to training, validation, and test data.

### Dependencies

pytorch 2.2.2
numpy 1.26.3
A GPU is assumed to be available for training; you can try modifying the code to run without one but it will be a very
slow process.

### Executing program

The notebook should be executed sequentially, with appropriate changes to the file paths.

## Authors

Obed Camacho\\
River Robles
