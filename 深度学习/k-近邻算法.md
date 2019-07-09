## k-邻近算法

对未知类别属性的数据集中的每个点依次执行以下操作：
- 计算已知类别数据集中的所有点与当前点之间的距离；
- 按照距离递增次序排序；
- 选取与当前点距离最小的k个点；
- 确定前k个点所在类别的出现频率；
- 返回前k个点出现频率最高的类别作为当前点的预测分类。

```
from numpy import * #科学计算包
import operator #运算符模块

def createDataSet():
    group = array([[1.0,1.1],[1.0,1.0],[0,0],[0,0.1]])
    labels=['A','A','B','B']
    return group,labels

group ,labels=createDataSet()

# inX  当前点
# dataSet 已知类别的数据集
# lebels 已知类别的数据集的类别
# k k个近邻点
def classify0(inX,dataSet,labels,k):
    #计算已知类别数据集中的所有点与当前点之间的距离
    dataSetSize=dataSet.shape[0] # shape是numpy中查看矩阵的维数的方法，3乘4的矩阵返回(3,4)，取shape[0]即是查看第一维度中有多少个，是数据集的大小3。
    diffMat=tile(inX,(dataSetSize,1))-dataSet # 先将当前点复制了已知数据集的份数，形成一个矩阵，再减去已知数据集，得到一个差值的列表
    sqDiffMat=diffMat**2 #平方
    sqDistance=sqDiffMat.sum(axis=1) #按轴1累加求和得到一个一维数组，代表平方和
    distance=sqDistance**0.5#开根号
    #按照距离递增次序排序
    sortedDIstIndicies=distance.argsort()#距离排序，并返回索引index，也就是下标
    #选取与当前点距离最小的k个点
    #确定前k个点所在类别的出现频率
    classCount={}#类别出现次数统计map集合
    for i in range(k):
        voteIlabel=labels[sortedDIstIndicies[i]]
        classCount[voteIlabel]=classCount.get(voteIlabel,0)+1
    #返回前k个点出现频率最高的类别作为当前点的预测分类
    sortedClassCount=sorted(classCount.items(),key=operator.itemgetter(1),reverse=True)
    return sortedClassCount[0][0]

# print (classify0([0,0],group,labels,3))
```
