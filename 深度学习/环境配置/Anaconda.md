## 安装Anaconda
第一步：首先安装anaconda3-5.1版本
下载地址：https://repo.continuum.io/archive/

安装过程中注意两点：
- 勾选所有用户
- 勾选配置环境变量

---
## Anaconda虚拟环境
进入工作目录
```
cd 工作目录
```
建立TensorFlow Anaconda虚拟环境：
```
conda create --name tensorFlow python=3.5 anaconda
```

启动Anaconda虚拟环境
```
activate tensorFlow
```

关闭Anaconda虚拟环境
```
deactivate tensorflow
```

---
## 安装TensorFlow：

启动Anaconda虚拟环境
```
activate tensorFlow
```

安装TensorFlow的CPU版本
```
pip install tensorFlow
```
遇到问题:
- Cannot uninstall 'wrapt'. It is a distutils installed project and thus we cannot accurately determine which files belong to it which would lead to only a partial uninstall.
```
pip install -U --ignore-installed wrapt enum34 simplejson netaddr
```
- distributed 1.21.8 requires msgpack, which is not installed.
```
pip install msgpack
```
```
pip install msgpack-python
```

安装Keras
```
pip install keras
```

---
## 启动Jupyter Notebook
进入工作目录
```
cd 工作目录
```
启动Anaconda虚拟环境
```
activate tensorFlow
```
启动Jupyter Notebook
```
jupyter notebook
```

---
## 测试环境
在jupyter notebook中导入，并查看版本
```
import tensorflow as tf
tf.__version__
```

```
import keras
keras.__version__
```
![img](../../imgs/9ab8c8a2-db52-11e9-8a34-2a2ae2dbcce4.png)
环境构建成功！

---

## GPU版本
进入工作目录

建立GPU版本的TensorFlow Anaconda虚拟环境
```
conda create --name tensorFlow-gpu python=3.5 anaconda
```

启动Anaconda虚拟环境
```
activate tensorFlow-gpu
```

安装TensorFlow的GPU版本
```
pip install tensorFlow-gpu==1.12
```
如果有相应的报错则安装
```
pip install --ignore-installed wrapt
```
和
```
pip install --ignore-installed  setuptools
```


安装Keras
```
pip install keras==2.2.4
```

安装PyTorch
conda：
 ```
conda install pytorch torchvision cudatoolkit=9.0 -c pytorch
 ```
或者pip
```
pip install https://download.pytorch.org/whl/cu90/torch-1.0.1-cp35-cp35m-win_amd64.whl
```
也可将
https://download.pytorch.org/whl/cu90/torch-1.0.1-cp35-cp35m-win_amd64.whl
下载到本地
然后
```
pip install 本地路径/torch-1.0.1-cp35-cp35m-win_amd64.whl
```
最后
```
pip install torchvision
```

全部对应Python3.5的版本

---
卸载
```
pip uninstall tensorflow-gpu
```
