# Neck Muscle Segmentation

<p align="center">
<img src="https://github.com/kennethaweberii/Neck_Muscle_Segmentation/blob/main/segmentation_figure.jpg" width="500">
</p>

This model was developed using NiftyNet. NiftyNet is a TensorFlow-based open-source convolutional neural networks (CNN) platform for research in medical image analysis. The model and code here have been tested on an Ubuntu 18.04.5 LTS workstation using only the CPU.

https://github.com/NifTK/NiftyNet

https://github.com/NifTK/NiftyNet/blob/dev/LICENSE

### Installation

1. Install conda: https://www.anaconda.com/
2. Download Neck_Muscle_Segmentation code and unzip if necessary. 
3. Download the model file here: https://office365stanford-my.sharepoint.com/:u:/g/personal/kenweber_stanford_edu/EZjYg_yWeeRKtlWEi3IlmmoBuggmrsdsCCx9QFwXsvuKkw?e=bgNNvE
    * File is >100 MB and too big for GitHub
4. Copy model.ckpt-100000.meta into ./Neck_Muscle_Segmentation/neck_muscle_segmentation_model/models/
5. In the command line, navigate to the Neck_Muscle_Segmentation folder
6. Create a conda environment:
    * conda env create -f environment_cpu.yml
      * Use environment_gpu.yml if you want to use GPU version of tensorflow (Not tested)
7. Activate the conda environment:
    * conda activate Neck_Muscle_Segmentation
8. In a text editor, open inference.ini, and update path_to_search, filename_contains, and filename_not_contains to the folder with the IP and OP images
9. Run net_segment command to perform segmentations:
    * net_segment -c inference.ini inference

### Image Formatting Requirements

The model requires that the both the IP (in-phase) and OP (out-of-phase) images are present. The images should be in NIFTI format with separate files for the IP and OP images.

To convert DICOM to NIFTI, you can use: https://github.com/rordenlab/dcm2niix

### Citing Neck Muscle Segmentation Model

If you use use this model in your work, please cite:

* K. A. Weber 2nd, R. Abbott, V. Bojilov, A. C. Smith, M. Wasielewski, T. J. Hastie, T. B. Parrish, S. Mackey, and J. M. Elliott. Multi-muscle deep learnng segmentation to automate the quantification of muscle fat infiltration in cervical spine conditions, _Scientific Reports_., 2021;11(1):16567.
(https://doi.org/10.1038/s41598-021-95972-x)

### Citing NiftyNet

If you use this model in your work, please cite:

* E. Gibson, W. Li, C. Sudre, L. Fidon, D. I. Shakir, G. Wang, Z. Eaton-Rosen, R. Gray, T. Doel, Y. Hu, T. Whyntie, P. Nachev, M. Modat, D. C. Barratt, S. Ourselin, M. J. Cardoso, and T. Vercauteren†. NiftyNet: a deep-learning platform for medical imaging. _Computer Methods and Programs in Biomedicine_, 2018;158:113-122.
(https://doi.org/10.1016/j.cmpb.2018.01.025)
