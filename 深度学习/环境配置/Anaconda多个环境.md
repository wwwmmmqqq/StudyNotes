所有的python版本和现在的分支：
```
conda info –-envs
```

创建一个python3.5的新的环境：
```
conda create --name <环境名称> python=3.5
```

复制一个环境：
```
conda create -n <新的名称> --clone <源环境名称>
```

删除环境：
```
conda remove -n <环境名称> --all  
```
