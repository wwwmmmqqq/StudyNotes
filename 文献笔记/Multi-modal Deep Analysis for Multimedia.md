传统的多模式分析方法可以分为两类：特征融合和语义融合。

特征融合（也称为特征工程）方法仅对来自不同模态的原始特征进行特征级联，通常这是通过手动操作实现的，效率非常低。

语义融合首先从一开始就分别从单个模态分析信息，然后在语义级别进行多模态融合。这种方法可以保持语义融合中的可解释性，但不能充分利用隐藏在多模式中的丰富信息。

---

 ## 数据驱动的多模态相关表示

### 多任务学习和多视图学习
多模态/跨媒体相关表示法寻求一种在公共空间中表示不同模态数据的方法，以使来自每个模态的数据变得彼此可比，并且可以将它们原始空间中的尽可能多的属性保留在公共空间中。

- #### 多任务学习

&emsp;&emsp;旨在通过发现多个任务之间的关系来同时学习不同的任务。多任务学习中最重要的策略之一是要同时考虑多个任务之间的差异和联系，这种策略已广泛用于多标签分类，人脸识别等方面。
&emsp;&emsp;多任务学习可以大致分为两类：
1. 强制多个任务共享相同参数的方法；
2. 挖掘多个任务之间共同潜在特征的方法；

&emsp;&emsp;[“Regularized multi–task learning,” in Proceedings of the tenth ACM SIGKDD international conference on Knowledge discovery and data mining]()提出了正则多任务学习，这是一个关于公共参数的代表性模型，可在学习过程中最小化正则函数。将多任务学习的概念与单任务SVM相结合，并说明了不同的单SVM任务之间的联系。假定所有任务共享一个公共的中央分隔超平面，该平面又通过偏移参数确定当前任务的最终决策边界。

&emsp;&emsp;至于挖掘潜在特征的方法，[“Convex multi-task feature learning,” Machine Learning, vol. 73, no. 3, pp. 243–272, 2008]()提出了一个典型的凸多任务特征学习框架，为后来的多任务学习算法奠定了基础。

&emsp;&emsp;在[“Multitask sparsity via maximum entropy discrimination,” Journal of Machine Learning Research, vol. 12, no. Jan, pp. 75–110, 2011]()中，从特征选择，内核选择，自适应池和图形模型结构方面讨论了四组多任务学习算法。

&emsp;&emsp;有关更多详细信息，请参阅调查文章[A Survey on Multi-Task Learning](https://arxiv.org/abs/1707.08114)和[An overview of multi-task learning in deep neural networks](https://arxiv.org/abs/1706.05098)。

- #### 多视图学习

&emsp;&emsp;多视图学习通过使用一个功能为每个视图建模并共同优化所有功能，从相同的输入数据中考虑多个视图，从而可以最好地利用多视图的信息，从而提高学习性能可以大大改善。与多任务学习（输入数据可能来自多个任务）不同，多视图学习将同一任务的不同视图用作输入。这些不同的视图可以是识别任务中的人脸ID和指纹，或图像表示任务中的颜色和文字。

&emsp;&emsp;多视图学习可分为三种类型：
1. 协同训练：训练模型以使未标记数据的两个不同视图之间的相互一致性最大化。
2. 多核学习：将对应于不同视图的不同核组合在一起，以提高性能；
3. 子空间学习：假设存在一个由所有视图共享的公共潜在子空间，以便可以从该共享的潜在子空间生成不同的视图数据；

&emsp;&emsp;此外，有两个被广泛采用的原则，以确保可以充分利用来自多个视图的信息：
1. 共识原则（用于共同训练）：通过要求两个假设尽可能一致，来最大化两个视图之间的相互一致性。
2. 互补原则：每个不同的视图都有一些独特的信息。因此，我们可以通过充分利用来自不同角度的补充知识来提高学习效果。

&emsp;&emsp;参考有关多视图学习的概述文章[A survey on multi-view learning](https://arxiv.org/abs/1304.5634)，[“A survey of multi-view machine learning,” Neural Computing and Applications, vol. 23, no. 7-8, pp. 2031–2038, 2013]()。

### 多模态深度表示




























---



---
