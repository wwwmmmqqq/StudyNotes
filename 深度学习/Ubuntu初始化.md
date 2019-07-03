### 切换镜像

### 安装VM tools

### 更新pip
```
sudo pip3 install --upgrade pip
```

### 强制重新安装pip3
```
wget https://bootstrap.pypa.io/get-pip.py  --no-check-certificate

sudo python3 get-pip.py --force-reinstall
```

### pip安装时ReadTimeoutError解决办法
```
sudo pip3 --default-timeout=100 install gevent
```
