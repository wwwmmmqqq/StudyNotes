### pip
假设你已经安装了全新的 Ubuntu，并配备了 NVIDIA GPU。开始之前，请确认你已经安装了 pip，并确认你的包管理器是最新的。
```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install python3-pip python3-dev
```



### 安装 Python 科学套件
安装 BLAS 库（这里安装的是 OpenBLAS），确保你可以在 CPU 上运行快速的张量运算。
```
sudo apt-get install build-essential cmake git unzip \
 pkg-config libopenblas-dev liblapack-dev
```

安装 Python 科学套件：Numpy、SciPy 和 Matplotlib。无论是否做深度学习，如果想要
使用 Python 进行任意类型的机器学习或科学计算，这一步都是必需的。
```
sudo apt-get install python3-numpy python3-scipy python3-matplotlib python3-yaml
```

安装 HDF5。这个库最初由 NASA（美国国家航空航天局）开发，用高效的二进制格式
来保存数值数据的大文件。它可以让你将 Keras 模型快速高效地保存到磁盘。
```
sudo apt-get install libhdf5-serial-dev python3-h5py
```

安装 Graphviz 和 pydot-ng，这两个包可以将 Keras 模型可视化。它们对运行 Keras 并不
是必需的，所以你可以跳过这一步，在需要时再来安装这些包。安装命令如下。
```
sudo apt-get install graphviz
sudo pip install pydot-ng
```

安装某些代码示例中用到的其他包。
```
sudo apt-get install python3-opencv
```

### 安装 TensorFlow

无论是否支持 GPU，都可以使用 pip 从 PyPI 安装 TensorFlow。安装不支持 GPU 的
TensorFlow 的命令如下。
```
sudo pip3 install tensorflow
```
安装支持 GPU 的 TensorFlow 的命令如下。
```
sudo pip3 install tensorflow-gpu
```

### 安装 Keras
可以从 PyPI 安装 Keras。
```
sudo pip3 install keras
```
或者也可以从 GitHub 安装 Keras。这么做的话，就可以访问 keras/examples 文件夹，里面
包含许多示例脚本供你学习。
```
git clone https://github.com/fchollet/keras
cd keras
sudo python setup.py install
```
现在你可以尝试运行一个 Keras 脚本，比如这个 MNIST 示例。
```
python3 examples/mnist_cnn.py
```
注意，完整运行这个示例可能需要几分钟。因此，在确认 Keras 可以正常运行之后，你可
以随时强制退出（按 Ctrl-C）。
运行 Keras 至少一次之后，就可以在 ~/.keras/keras.json 找到 Keras 的配置文件。你可以编
辑这个文件，选择运行 Keras 的后端：tensorflow、theano 或 cntk。你的配置文件应该是
这样的。
```
{
  "image_data_format": "channels_last",
  "epsilon": 1e-07,
  "floatx": "float32",
  "backend": "tensorflow"
}
```
运行 examples/mnist_cnn.py 这个 Keras 脚本时，你可以在另一个 shell 窗口中监控 GPU 利
用率。
```
watch -n 5 NVIDIA-smi -a --display=utilization
```
一切安装完成，恭喜你！现在可以开始构建深度学习应用了。

### 设置 GPU 支持


### 安装 Theano（可选）
