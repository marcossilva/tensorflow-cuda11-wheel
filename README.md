# Tensorflow 2.4 Cuda 11 Wheel

If you are on Ubuntu 20.04 with CUDA 11.0 and want a pre-built wheel for tensorflow then you're in the right place!


## Introduction

Recently CUDA 11 was released together with a newer version of CuDNN. The prebuil wheel available on pip still hasn't been built for these so I decided to build manually. As it's a time consuming task I tought it would be nice to share in case anyone decides to do the same. I've let the configuration mostly untouched and all the available optimizations were built. As building for different computing capabilities is extremely time consuming I've only built for mine (sorry)
## Available Wheels

|TensorFlow|Python|CUDA|CuDNN|Compute Capability|OS|Link|
|---:|---:|---:|---:|---:|---:|---:|
|2.4.0|3.8|11.0|8.0|5.2|Ubuntu 20.04|[tensorflow-2.4.0-cp38-cp38-linux_x86_64.whl](https://github.com/marcossilva/tensorflow-cuda11-wheel/releases/download/v2.4.0/tensorflow-2.4.0-cp38-cp38-linux_x86_64.whl)|
|2.4.0|3.8|11.0|8.0|6.1|Ubuntu 20.04|[tensorflow-2.4.0-cp38-cp38-linux_x86_64.whl](https://github.com/marcossilva/tensorflow-cuda11-wheel/releases/download/v2.4.1/tensorflow-2.4.0-cp38-cp38-linux_x86_64.whl)|
## Installation

Assuming you have all the requirements, you can install the wheel directly via pip:

```
pip install https://github.com/marcossilva/tensorflow-cuda11-wheel/releases/download/v2.4.0/tensorflow-2.4.0-cp38-cp38-linux_x86_64.whl
```
And verify the installation (notice no warning messages):

```
$ python
PPython 3.8.2 (default, Apr 27 2020, 15:53:34) 
[GCC 9.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import tensorflow as tf
2020-07-22 01:06:42.948959: I tensorflow/stream_executor/platform/default/dso_loader.cc:48] Successfully opened dynamic library libcudart.so.11.0
>>> print(tf.__version__)
2.4.0
>>> tf.executing_eagerly()
True
>>> tf.constant([123]) + tf.constant([321])
2020-07-22 01:07:08.259753: I tensorflow/stream_executor/platform/default/dso_loader.cc:48] Successfully opened dynamic library libcuda.so.1
...
2020-07-22 01:07:08.754953: I tensorflow/core/common_runtime/gpu/gpu_device.cc:1402] Created TensorFlow device (/job:localhost/replica:0/task:0/device:GPU:0 with 3173 MB memory) -> physical GPU (device: 0, name: GeForce GTX 980M, pci bus id: 0000:01:00.0, compute capability: 5.2)
<tf.Tensor: shape=(1,), dtype=int32, numpy=array([444], dtype=int32)>

```
