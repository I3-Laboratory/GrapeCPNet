# GrapeCPNet
Paper: GrapeCPNet: A deep learning integration for grape completion and phenotyping in 3D  

# Test Data and Weights are available here:
Please fill out the [form here](https://forms.gle/dDQwvTrHGtZebAG59) to receive the download link

When you download the dataset, please run the example by following the steps: 

Data and weight loading method:
1. Dataset:
(1). Introduction to the self-collected dataset used in the paper:
For individual grapes, point cloud data in. ply format is obtained through multi view reconstruction method, and each berry point cloud instance is manually cropped and converted to. txt format.
(2). Model loading point cloud data:
a. The data format of the segmentation model refers to the publicly available dataset S3DIS, and follows the organizational structure and data format. For specific details, please refer to it:
https://github.com/thangvubk/SoftGroup/blob/main/dataset/README.md
b. The data format of the completion model refers to the publicly available dataset PCN, and follows the organizational structure and data format. For specific details, please refer to it:
https://drive.google.com/file/d/17pE2U2T2k4w1KfmDbL6U-GkEwD-duTaF/view?usp=share_link
(3). Data format conversion:
Due to the original data being in. txt format, there is no data format conversion when converting to S3DIS specification (. txt), only the data set placement needs to be adjusted according to the data organization structure. At the same time, after obtaining a single incomplete berry (. txt) format through the segmentation model, it needs to be converted to .pcd format to comply with the PCN data format specification, and the data organization structure needs to be adjusted.
2. Weight loading:
(1) Method for loading weights of segmentation model:
The segmentation model specifies the storage location and parameter settings of data and weights through the .yaml files. At the same time, the segmentation model is divided into two parts: backbone training and overall network training (only the weights obtained from overall training are needed for testing). Specific reference:
https://github.com/thangvubk/SoftGroup/blob/main/configs/softgroup/softgroup_s3dis_backbone_fold5.yaml
(2) Method for loading model weights:
The completion model by specifying the pre-trained weights to be loaded through terminal commands:
python test.py –ckpt_path xxx ……，
Specific reference:
https://github.com/yuxumin/PoinTr/tree/master/models
