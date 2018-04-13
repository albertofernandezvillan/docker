# Steven Puttemans' Docker Repository: a repository containing my working docker configurations for others to freely use

Free to use, under the MIT license.

Comments or questions, address the [issues tab](https://github.com/StevenPuttemans/docker/issues)!

## Docker files

### Dockerfile_basic

My basic starting point for computer vision programming
 * Ubuntu 16.04 x64 OS
 * CUDA v8.0 with cuDNN v7.1
 * OpenCV 3.4.1 (current master) with following explicit set suboptions
	* CUDA support for compute capability 6.1 (NVidia Titan X, NVIDIA Quadro P5000)
	* TBB support
 	* Implementation collection enabled
 	* Python2 and Python3 support

If you build the docker from scratch, it will always pull the latest master branch of OpenCV.

### Dockerfile_darknet

Starts from the `Dockerfile_basic`-configuration, then applies the following extra's
 * Due to conflicts in OpenCV master branch, fix on release `3.4.0`
 * Download [EAVISE specific darknet repo](https://gitlab.com/EAVISE/darknet) and configures it to be build with CUDA and cuDNN support

### Dockerfile_segnet

A clean installation of the SegNet framework with
 * Ubuntu 16.04 x64 OS
 * CUDA v8.0 with cuDNN v5.0
 * Caffe with cuDNN v5.0 support from https://github.com/StevenPuttemans/caffe-segnet-cudnn5/

On top of that the SegNet repository is pre-installed and all pre-requisites for doing training, inference and post-analysis is already installed.

### Dockerfile_scannet

A clean installation of the ScanNet framework with
 * Ubuntu 16.04 x64 OS
 * CUDA v8.0 with cuDNN v5.0
 * Torch v7 installation based on the lua language

On top of that the ScanNet repository is pre-installed and all pre-requisites for doing training, inference and post-analysis is already installed.

### Dockerfile_pixelnet

Starts from the `Dockerfile_basic`-configuration, then applies the following extra's
 * Adds extra dependencies needed for caffe support
 * Builds latest master branch of caffe on 11/04/2018, with [adapted Makefile configuration](https://github.com/StevenPuttemans/caffe)
 * Download the available pixelnet framework

**TO DO**: add Matlab installation and configure the wrappers properly for setting up training and testing
