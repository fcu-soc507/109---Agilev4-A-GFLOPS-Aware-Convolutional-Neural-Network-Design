# 109-呂侑達-Agilev4
## Outline

## Source
github: [darknet](https://github.com/AlexeyAB/darknet)

detail information: [darknet-wiki](https://github.com/AlexeyAB/darknet/wiki)

## Agilev4
> Agilev4
>> Model Introduction

Model         | Backbone  | Neck | Model size | Input size | GFLOPS
--------------|-----------|------|------------|------------|-------
Agilev3       | 1,2,2,2   |  FPN |    65.5    | 512x512    | 49.5
Agilev4       | 1,15,15,8 |  FPN |  116.9     | 512x512    | 49.36

>> FPS on Nvidia Jetson Nano by tensorRT
The step of darknet model to trt model is from [jkjung-avt/tensorrt_demos](https://github.com/jkjung-avt/tensorrt_demos)


Model         | Input size | FPS
--------------|------------|-----
Agilev3       | 1,2,2,2    |7.22
Agilev4       | 1,15,15,8  |7.23

## Install
Step by step:
```python=
git clone https://github.com/AlexeyAB/darknet.git
cd darknet
make
git clone https://github.com/fcu-soc507/109-Agilev4.git
```
Put [agilev4.weights](https://drive.google.com/file/d/1rjc-SiBnINQKSdr47IK99MeC4Csmqu8I/view?usp=sharing) into "109-Agilev4" folder

![image](https://github.com/fcu-soc507/109-Agilev4/blob/main/image/folder.jpg)

## Inference
```python=
./darknet detector test 109-Agilev4/coco.data 109-Agilev4/agilev4.cfg 109-Agilev4/agilev4.weights data/dog.jpg
```
