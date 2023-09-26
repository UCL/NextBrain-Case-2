# BrainAtlas-P41-16
This repository contains data that is consumed by the [BrainAtlas project](https://github.com/UCL/BrainAtlas). This data corresponds to patient P41-16. For the source code of this project refer to the main [BrainAtlas repo](https://github.com/UCL/BrainAtlas).

## Data structure
This brain specimen has been cut into 41 blocks including cerebrum, cerebellum and brain stem. The histology-related data is organised following a numbered list of blocks, from 1 to 41. 

The struture of the dataset is as follows:
- [Histology](#histology)
- [High-resolution histology](#histology_hr)
- [MRI](#mri_rotated)
- [Util files](#utils)


<div id='histology'/>
  
### Histology

This directory contains data on the histology space at 0.1mm in-plane resolution. 
For each block, we provide the following data:
 - __slices_HE__: HE stained slices non-linearly aligned to the corresponding MRI section (.jpg extension).
 - __slices_LFB__: LFB stained slices non-linearly aligned to the corresponding MRI section (.jpg extension).
 - __slices_MRI__: MRI sections corresponding to histology slices (.jpg extension).
 - __slices_labels__: structure labels delineated on the LFB slice and non-linearly aligned to the corresponding MRI section (.png extension).
 - __slices_labels_npz__: structure labels delineated on the LFB slice and non-linearly aligned to the corresponding MRI section (.npz extension).
 - __matrix.txt__: affine matrix that relates the block (stack of images) and the MR image.

<div id='histology_hr'/>
  
### High-resolution histology

This directory contains data on the histology space at 1.9844um in-plane resolution. 
For each block, we provide the following data:
 - __slices_HE__: HE stained slices non-linearly aligned to the corresponding MRI section (.jpg extension).
 - __slices_LFB__: LFB stained slices non-linearly aligned to the corresponding MRI section (.jpg extension).
 - __slices_MRI__: masked MRI sections corresponding to histology slices (.jpg extension).
 - __slices_labels__: structure labels delineated on the LFB slice and non-linearly aligned to the corresponding MRI section (.png extension).
 - __slices_labels_npz__: structure labels delineated on the LFB slice and non-linearly aligned to the corresponding MRI section (.npz extension).
 - __matrix.txt__: affine matrix that relates the block (stack of images) and the MR image.


<div id='mri_rotated'/>
  
### MRI

- __mri.nii.gz__: MRI scan.
- __indices.nii.gz__: volume containing the 3D version of the corresponding block to each voxel on the MRI scan.
- __slices_{axial/sagittal/coronal}__: MRI slices in each direction on the MRI space.  (.png extension)
- __indices_{axial/sagittal/coronal}__: 2D integer image containing the block number corresponding to each voxel on the MRI slice  (.npy extension)
- __matrices{/_hr}__: affine matrices that relate the MRI image with each block.


<div id='utils'/>
  
### Util files

- __histologyDimensionsKey.json__: metadata corresponding to the *histology* directory. It contains the image size and number of slices for each block, as well as the orientation of the acquisition.
- __histologyHRDimensionsKey.json__: metadata corresponding to the *histology_hr* directory. It contains the image size and number of slices for each block, as well as the orientation of the acquisition.
- __mriDimensionsKey.json__: metadata corresponding to the *mri* directory. It contains the image size and number of slices in each orthogonal direction.
- __image_ontology_hierarchical.json__: it contains the label ontology used to delinate brain structures split into two levels: the first one correspond to high-level ROI structures while the second contains the nuclei in each structure. Moreover, it contains the centroid voxel of each nuclei on MRI space $(x_m, y_m, z_m)$ and on histological space $(x_h, y_h, z_h)$
	

## Additional BrainAtlas patient data:
* [P57-16](https://github.com/UCL/BrainAtlas-P57-16)
* [P58-16](https://github.com/UCL/BrainAtlas-P58-16)
* [P85-18](https://github.com/UCL/BrainAtlas-P85-18)
* [EX9-19](https://github.com/UCL/BrainAtlas-EX9-19)

