# BP-Layers
This repository contains the implementation for our publication "Belief Propagation Reloaded: Learning BP-Layers for Labeling Problems". If you use this implemenation please cite the following publication:

~~~
@InProceedings{Knobelreiter_2020_CVPR,
  author = {Knöbelreiter, Patrick and Sormann, Christian and Shekhovtsov, Alexander and Fraundorfer, Friedrich and Pock, Thomas},
  title = {Belief Propagation Reloaded: Learning BP-Layers for Labeling Problems},
  booktitle = {The IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
  month = {June},
  year = {2020}
} 
~~~

<p align="center"><img width=100% src="github_imgs/teaser.gif"></p>

## Repository Structure

The repository is structured as follows:
    - the base directory contains scripts for running inference and python implementations of the networks
    - 'data' includes sample images for stereo/semantic/flow inference
    - 'ops' contains custom PyTorch-Ops which need to be installed before running the respective stereo/semantic implementation (note that this is also taken care of by the run_*.sh scripts)

## Dependencies

* Cuda 10.2
* pytorch >= 1.3
* argparse
* imageio
* numpy


## Running the implementation

After installing all of the required dependencies above you can run the implementation for specific tasks via the respective shell scripts. We provide the following files:

### Stereo
* run_stereo_sf.sh: The models trained on the Scene-Flow Dataset
* run_stereo_mb.sh: The model used for evaluation on the Middlebury dataset
* run_stereo_kitti: The model used for evaluation on the Kitti dataset

<img width=45% src="data/im0.png">
<img width=45% src="github_imgs/mb.png">

<img width=45% src="data/000010_10_left.png">
<img width=45% src="github_imgs/kitti.png">

<img width=45% src="data/sf_0006_left.png">
<img width=45% src="github_imgs/sf.png">


### Flow
* run_flow.sh

<p align="center"><img width=45% src="data/frame_0019.png">
<img width=45% src="github_imgs/flow_example.png"></p>

### Semantic Segmentation
* run_semantic_global.sh: Our semantic segmentation model with *global* pairwise weights
* run_semantic_pixel: Our semantic segmentation model with *pixel-wise* pairwise weights




~~~
sh run_semantic_pixel.sh
~~~

Should yield this result:

<p align="center"><img width=45% src="github_imgs/sem_input.png">
<img width=45% src="github_imgs/sem_pred.png"></p>

Inside these scripts you can also specify different images to be used for inference. The correct PyTorch-Ops are also automatically installed by these scripts before running the inference. 