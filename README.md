# 109-呂侑達-Agilev4
## Outline

## Source
github: [darknet](https://github.com/AlexeyAB/darknet)

detail information: [darknet-wiki](https://github.com/AlexeyAB/darknet/wiki)
## Install
Step by step:
```python=
git clone https://github.com/AlexeyAB/darknet.git
cd darknet
make
git clone https://github.com/fcu-soc507/109-Agilev4.git
```
Put [agilev4.weights](https://drive.google.com/file/d/1rjc-SiBnINQKSdr47IK99MeC4Csmqu8I/view?usp=sharing) into "109-Agilev4" folder
## Inference
```python=
./darknet detector test 109-Agilev4/coco.data 109-Agilev4/agilev4.cfg 109-Agilev4/agilev4.weights data/dog.jpg
```
