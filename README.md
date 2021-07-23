### DCGAN

### 概述
迁移dcgan到ascend910平台上使用NPU运行，并将结果与原论文进行对比

### Requirements
Python 3.6
Tensorflow 1.15
SciPy
pillow
tqdm

Ascend: 1*Ascend 910 CPU: 24vCPUs 96GiB

### 代码及路径解释
```
DCGAN
└─
  ├─README.md
  ├─LICENSE  
  ├─download.py 获取数据集，在NPU上不适用
  ├─main.py     执行主函数代码
  ├─model.py    定义模型结构
  ├─ops.py      自定义算子
  ├─utils.py    工具函数
  
  
```
### 数据集和预训练模型：

数据集：ILSVRC2012_img_train

链接：https://image-net.org/data/ILSVRC/2012/ILSVRC2012_img_train.tar

OBS桶地址：obs://xubinxbchen/imagenet/


### 训练过程及结果


### ModelArts参数
```dataset=imagenet;input_height=256;input_width=256;train=true;crop=true;input_fname_pattern=*.JPEG;epoch=5;learning_rate=0.0002;batch_size=64;out_name=""```


### 执行训练

python main.py 


主要参数注释：
```
dataset: dataset name

data_dir: dataset url

train: is train

input_height: 

output_height: 

```

### AutoTune调优
https://support.huaweicloud.com/tensorflow-cann330alpha2training/atlasmprtg_13_0054.html