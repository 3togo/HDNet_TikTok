# Learning High Fidelity Depths of Dressed Humans by Watching Social Media Dance Videos

[![report](https://img.shields.io/badge/arxiv-report-red)](https://arxiv.org/abs/2103.03319)

This repository contains a tensorflow implementation of "[Learning High Fidelity Depths of Dressed Humans by Watching Social Media Dance Videos](https://arxiv.org/abs/2103.03319)" in CVPR 2021 **(Oral Presentation)**.

[Project Page](https://www.yasamin.page/hdnet_tiktok)

![Teaser Image](https://github.com/yasaminjafarian/HDNet_TikTok/blob/main/figures/TikTok1.gif)


This codebase provides: 
- Inference code          (Comming soon!)
- Visualization code      (Comming soon!)
- Training code           (Comming soon!)

## Requirements
(This code is checked with tensorflow-gpu version 1.14.0, Python 3.7.4, CUDA 10 (version 10.0.130) and cuDNN 7 (version 7.4.2).)
- numpy
- imageio
- matplotlib
- scikit-image
- scipy==1.1.0
- tensorflow-gpu==1.14.0
- gast==0.2.2
- Pillow

## Installation
Run the following code to install all pip packages:
```sh
pip install -r requirements.txt 
```
In case there is a problem, you can use the following tensorflow docker container "[(**tensorflow:19.02-py3**)](https://docs.nvidia.com/deeplearning/frameworks/tensorflow-release-notes/running.html)":
```sh
sudo docker run --gpus all -it --rm -v local_dir:container_dir nvcr.io/nvidia/tensorflow:19.02-py3
```
Then you can install the requirements:
```sh
pip install -r requirements.txt 
```
## Inference Demo

#### Input:
The test data dimension should be: 256x256. For any test data you should have 3 **.png** files: (For an example please take a look at the demo data in "test_data" folder.)
- **name_img.png**  : The 256x256x3 test image 
- **name_mask.png** : The 256x256 corresponding mask. You can use any off-the-shelf tools such as [removebg](https://www.remove.bg/) to remove the background and get the mask. 
- **name_dp.png**   : The 256x256x3 corresponding [DensePose](http://densepose.org/). 

#### Output:
Running the demo will provide you with the following:
- **name.txt**  : The 256x256 predicted depth
- **name_mesh.obj** : The reconstructed mesh. You can use any off-the-shelf tools such as [MeshLab](https://www.meshlab.net/) to visualize the mesh.
- **name_normal_1.txt, name_normal_2.txt, name_normal_3.txt**   : Three 256x256 predicted normal. If you concatenate them in the third axis it will give you the 256x256x3 normal map.
- **name_results.png**  : visualization of predicted depth heatmap and the predicted normal map.



## Citation
If you find the code useful in your research, please consider citing the paper.

```
@InProceedings{jafarian2021tiktok,
author={Yasamin Jafarian and Hyun Soo Park},
title = {Learning High Fidelity Depths of Dressed Humans by Watching Social Media Dance Videos},
booktitle = {CVPR},
year = {2021}}
```
