# 109-呂侑達-Agilev4
## Outline
[TOC]
## 資料來源
github: [darknet](https://github.com/AlexeyAB/darknet)

詳細說明: [darknet-wiki](https://github.com/AlexeyAB/darknet/wiki)
## Install
執行以下指令:
```python=
git clone https://github.com/AlexeyAB/darknet.git
cd darknet
make
git clone https://github.com/fcu-soc507/109-Agilev4.git
```
請將 [agilev4.weights](https://drive.google.com/file/d/1rjc-SiBnINQKSdr47IK99MeC4Csmqu8I/view?usp=sharing)放到109-Agilev4資料夾裡面
## Inference
```python=
./darknet detector test 109-Agilev4/coco.data 109-Agilev4/agilev4.cfg 109-Agilev4/agilev4.weights data/dog.jpg
```
