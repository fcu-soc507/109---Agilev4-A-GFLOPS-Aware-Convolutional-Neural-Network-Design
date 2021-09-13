# 109-呂侑達-Agilev4
we propose the CNN model which we call Agilev4. It only needs 25% of the weight and 50% of the computation complexity of the well-known neural network to be used in certain application scenarios to obtain similar accuracy. Our first idea is that we should design a just-enough CNN model according to the target application scenario. If the general-purpose scenario is needed, our second idea is that we can increase the number of weights or the depth of the neural network to enhance detection accuracy while keeping the amount of computation complexity the same by adjusting the stride size of each neural layer and the number of convolution sets. 

<div align=center><img src="https://user-images.githubusercontent.com/50125053/133029547-4ee5decd-162d-450d-8cc6-ca57cac1e9f3.png"></div>

## Source
From from [yolov4](https://github.com/AlexeyAB/darknet).

The detail about yolov4 is [here](https://github.com/AlexeyAB/darknet/wiki).

## Agilev4
> Agilev4
>> Model Introduction

Model         | Backbone  | Neck | Model size | Input size | GFLOPS
--------------|-----------|------|------------|------------|-------
Agilev3       | 1,2,2,2   |  FPN |    65.5    | 512x512    | 49.5
Agilev4       | 1,15,15,8 |  FPN |  116.9     | 512x512    | 49.36

>> Model evaluate AP on the MS COCO evaluation server (test-dev2017)

>> FPS on Nvidia Jetson Nano by tensorRT
The step of darknet model to trt model is from [jkjung-avt/tensorrt_demos](https://github.com/jkjung-avt/tensorrt_demos)


Model         | backbone | FPS
--------------|------------|-----
Agilev3       | 1,2,2,2    |7.22
Agilev4       | 1,15,15,8  |7.23

## Install
```python=
git clone https://github.com/AlexeyAB/darknet.git
cd darknet
make
git clone https://github.com/fcu-soc507/109-Agilev4.git
```
place [agilev4.weights](https://drive.google.com/file/d/1rjc-SiBnINQKSdr47IK99MeC4Csmqu8I/view?usp=sharing) into "109-Agilev4" folder

![圖片](https://user-images.githubusercontent.com/50125053/133028759-5532a462-aff5-45d3-a8d1-d5fc4b80f2bc.png)

## command
>> training 
>> 
```python=
./darknet detector train 109-Agilev4/coco.data 109-Agilev4/agilev4.cfg 109-Agilev4/agilev4.weights data/dog.jpg -map -dont_show
```

>> test
>> 
```python=
./darknet detector test 109-Agilev4/coco.data 109-Agilev4/agilev4.cfg 109-Agilev4/agilev4.weights data/dog.jpg
```

>> cal map
>> 
```python=
./darknet detector map 109-Agilev4/coco.data 109-Agilev4/agilev4.cfg 109-Agilev4/agilev4.weights 
```
