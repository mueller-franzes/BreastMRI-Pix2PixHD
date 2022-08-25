# BreastMRI-Pix2PixHD
PyTorch implementation of the Pix2PixHD network for generating synthetic dynamic contrast enhanced (DCE) subtraction images from native (T1-/T2-weighted) sequences and low-dose contrast DCE subtraction images.


## Data Preprocessing
- Split into unilateral breasts and cut volumes into slices along the axial axis
- Resample images to 0.64 x 0.64 mm
- Crop or Zero-Pad Images to 256 X 224 Pixels  
- Stack [T2, T2, LowDose] into a 3-channel Image
- Scale Image to [0,1]
- Normalize each channel so that Mean = 0.5 and STD=0.5
- Store files as `.tiff` in a folder called `test_A` 

## Getting Started
* Eventually see instructions given in the  [Pix2PixHD repository](https://github.com/NVIDIA/pix2pixHD)  
* Change the following options in /options/base_options.py: 
    * `--name` select desired model from ./checkpoints. Name must match folder name, e.g. 'Lowdose_T2' 
    * `--dataroot` set to directory that contains 'test_A' eg. /mnt/datasets/breast/
* Change the following options in /options/test_options.py: 
    * `results_dir` set to desired output directory eg. '/mnt/datasets/breast/pred_B' 
* Run `test.py`


## Paper
Please see our paper at:

## Acknowledgments
This code is largely based on the Pix2PixHD repository.