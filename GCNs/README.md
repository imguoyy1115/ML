# 一、安装Miniconda（tensorflow1.15.0与当前版本不兼容），创建Python3.7环境
## 下载并安装Miniconda
```
!wget https://repo.anaconda.com/miniconda/Miniconda3-py37_4.10.3-Linux-x86_64.sh
!bash Miniconda3-py37_4.10.3-Linux-x86_64.sh -b -p /content/Miniconda3
```

## 把Conda的路径加入环境变量
```
import os
os.environ['PATH'] = "/content/Miniconda3/bin:" + os.environ['PATH']
```
## 创建名为tf1的Python3.7环境
```
!conda create -n tf1 python=3.7 -y
```
# 二、安装相关库和TensorFlow
## 安装所需库
```
!conda run -n tf1 pip install protobuf==3.20.3
!conda run -n tf1 pip install networkx
!conda run -n tf1 pip install scipy==1.4.1
```
## 安装tensorflow
```
!conda run -n tf1 pip install tensorflow==1.15.0
!conda run -n tf1 python -c "import tensorflow as tf; print(tf.__version__)"
```
# 三、克隆github并运行 https://github.com/imguoyy1115/gcn
## 克隆仓库
```
!git clone https://github.com/imguoyy1115/gcn
```
## 安装GCN项目库
```
%cd /content/gcn
!conda run -n tf1 python setup.py install
```
## 运行训练代码
```
%cd /content/gcn/gcn
!conda run -n tf1 python train.py
```
