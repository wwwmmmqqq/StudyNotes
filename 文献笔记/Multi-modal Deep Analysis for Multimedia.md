## 数据驱动的多模态相关表示

### A. 多任务学习和多视图学习
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

&emsp;&emsp;参考有关多视图学习的概述文章[A survey on multi-view learning](https://arxiv.org/abs/1304.5634)和[“A survey of multi-view machine learning,” Neural Computing and Applications, vol. 23, no. 7-8, pp. 2031–2038, 2013]()。

### B. 多模态深度表示

多模态方法主要可以分为两类：
- 特征融合方法[“Reducing the dimensionality of data with neural networks”，2006，第504–507页]()，[“Deep multimodal fusion” in The International Conference，2014，第34-41页]()：从每个模态提取的聚合特征并提供聚合特征模型（类似于特征工程的过程）
- 语义融合方法[“Combining modality specific deep neural networks for emotion recognition in video,” in ACM on International Conference on Multimodal Interaction, 2013, pp. 543–550]()、[“Two-stream convolutional networks for action recognition in videos,” pp. 568–576, 2014]()、[“Deep dynamic neural networks for multimodal gesture segmentation and recognition,” IEEE Transactions on Pattern Analysis & Machine Intelligence, vol. 38, no. 8, pp. 1583–1597, 2016]()：将每种模态的特征分别输入模型，并组合所有模型的结果以获得最终结果（类似于整体学习的方法）

&emsp;&emsp;特征融合适用于模态共享许多相关特征的问题，而语义融合方法则适合那些具有明显不相关模态的问题

可以根据多模态方法是判别型，生成型还是两者（混合型）进行分类。

- 判别模型通常学习给定特征的标签的条件分布[“Deep dynamic neural networks for multimodal gesture segmentation and recognition,” IEEE Transactions on Pattern Analysis & Machine Intelligence, vol. 38, no. 8, pp. 1583–1597, 2016]()、[“Deep fragment embeddings for bidirectional image sentence mapping,” vol. 3, pp. 1889–1897, 2014]()、[“Long-term recurrent convolutional networks for visual recognition and description,” in Computer Vision and Pattern Recognition, 2015, p. 677]()、[ “Exploring models and data for image question answering,” in International Conference on Neural Information Processing Systems, 2015, pp. 2953–2961]()、[“Deep convolutional and lstm recurrent neural networks for multimodal wearable activity recognition,” Sensors, vol. 16, no. 1, p. 115, 2015]()、[Multimodal residual learning for visual qa]()。
- 生成模型倾向于学习它们的联合分布[30]-[39]。
- 混合模型通过组合判别部分和生成部分来学习条件分布和联合分布[40] – [42]。

[30] J. Ngiam, A. Khosla, M. Kim, J. Nam, H. Lee, and A. Y. Ng, “Multimodal deep learning,” in Proceedings of the 28th international conference on machine learning (ICML-11), 2011, pp. 689–696.
[31] N. Srivastava and R. Salakhutdinov., “Learning representations for multimodal data with deep belief nets,” in International conference on machine learning workshop, vol. 79, 2012.
[32] N. Srivastava and R. R. Salakhutdinov, “Multimodal learning with deep boltzmann machines,” in Advances in neural information processing systems, 2012, pp. 2222–2230.
[33] C. Yu, S. Steffey, J. He, D. Xiao, T. Cui, P. Chen, and H. Mller, “Medical image retrieval: A multimodal approach,” vol. 13, no. Suppl 3, pp. 125–136, 2014.
[34] I. J. Goodfellow, J. Pouget-Abadie, M. Mirza, B. Xu, D. Warde-Farley, S. Ozair, A. Courville, and Y. Bengio, “Generative adversarial nets,” in International Conference on Neural Information Processing Systems, 2014, pp. 2672–2680.
[35] D. P. Kingma and M. Welling, “Auto-encoding variational bayes,” in Conference Proceedings: Papers Accepted To the International Conference on Learning Representations, 2014.
[36] Y. Huang, W. Wang, and L. Wang, “Unconstrained multimodal multilabel learning,” IEEE Transactions on Multimedia, vol. 17, no. 11, pp.
1923–1935, 2015.
[37] S. Reed, Z. Akata, X. Yan, L. Logeswaran, B. Schiele, and H. Lee, “Generative adversarial text to image synthesis,” pp. 1060–1069, 2016.
[38] M. Suzuki, K. Nakayama, and Y. Matsuo, “Joint multimodal learning with deep generative models,” 2016.
[39] G. Pandey and A. Dukkipati, “Variational methods for conditional multimodal deep learning,” in International Joint Conference on Neural Networks, 2017, pp. 308–315.
[40] M. R. Amer, B. Siddiquie, S. Khan, and A. Divakaran, “Multimodal fusion using dynamic hybrid models,” in Applications of Computer Vision, 2014, pp. 556–563.
[41] Y. Liu, X. Feng, and Z. Zhou, “Multimodal video classification with stacked contractive autoencoders,” Signal Processing, vol. 120, no. 4, pp. 761–766, 2015.
[42] M. R. Amer, T. Shields, B. Siddiquie, A. Tamrakar, A. Divakaran, and S. Chai, “Deep multimodal fusion: A hybrid approach,” International Journal of Computer Vision, vol. 126, no. 2-4, pp. 440–456, 2018.

&emsp;&emsp;有关多模式深度学习的调查论文[“Deep multimodal learning: A survey on recent advances and trends,” IEEE Signal Processing Magazine, vol. 34, no. 6, pp. 96–108, 2017]()。与调查论文不同，在这项工作中，我们重点关注与多媒体相关的领域中的多模式场景，包括但不限于基于深度神经网络的架构。

&emsp;&emsp;接下来，我们讨论两个利用领域适应的思想来桥接不同模式的深层表示的著作[44] [45]，这在所引用的调查论文中并未涉及。
&emsp;&emsp;我们从经典著作[“How transferable are features in deep neural networks?” in International Conference on Neural Information Processing Systems, 2014, pp. 3320–3328]()开始。

&emsp;&emsp;**在深度神经网络中的可传递性。**

&emsp;&emsp;结论是，对于给定的深度神经网络，更深层次的表示层更依赖于要解决的特定任务。浅层负责捕获更多一般特征。这一原则激励我们在深度学习中将这些较深的表示层适应于多模式任务。因此，Tzeng等，提出了一种具有代表性的方法（称为DCC）[Deep domain confusion: Maximizing for domain invariance]()，通过采用最大平均差异（MMD）[48]来减少八层AlexNet的第七层（在softmax之前）的两种模态之间的分歧，从而适应更深的层。

DCC有两个缺点：
1. 它仅适应深度神经网络（AlexNet）中的一个单层（即第七层）。正如Yosin ski等人所述，这可能还不够。[“How transferable are features in deep neural networks?” in International Conference on Neural Information Processing Systems, 2014, pp. 3320–3328]()指出，不止一层是可转让的。
2. 而且，它采用了单内核MMD（SK-MMD），它可能无法用作最佳内核。

&emsp;&emsp;为了解决这些弱点，Long等。提出了深度适应网络（DAN）[“Learning transferable features with deep adaptation networks,” pp. 97–105, 2015]()，该网络通过多核MMD（MK-MMD）同时适应三个深度层，该MMD能够通过将多个核组合在一起来生成最终的内核希尔伯特空间（RKHS），从而构造最终的核 ）。图3说明了深度适应网络（DAN）的体系结构。

DAN的目标则由两个部分组成：
1. 深度匹配，可以多种形式匹配表示层的分布；
2. 最佳匹配，可以通过RKHS中的MK-MMD最大化两个样本的测试能力。

&emsp;&emsp;另一方面，DAN也不完美，因为它与边际分布P（x）和Q（x）匹配，而不是联合分布P（x，y）和Q（x，y）。

&emsp;&emsp;如图4所示，匹配联合分布比匹配边际分布可以获得更好的性能。

&emsp;&emsp;因此，Long等人提出了一种基于联合适应网络（JAN）的模型[“Deep transfer learning with joint adaptation networks,” 2017]()。以匹配来自不同模块的深层表示之间的联合分布。

&emsp;&emsp;图5说明了联合适应网络（JAN）及其对抗版本（JAN-A）的结构。

&emsp;&emsp;由于RKHS既不是高维也不是无限维的，因此通常采用高斯核映射样本到无限空间作为核函数，并根据经验选择最终的带宽参数。

&emsp;&emsp;我们注意到，尽管这两部作品研究了不同（两种）模式之间的转移表示，但是它们的学习过程是双向的，所提出的模型可以在任何两种模式下进行测试，而实验中对“源”或“目标”域没有固定要求。因此，我们将这两部作品归类为多模式深度表示而不是多模式转移学习。

&emsp;&emsp;除了领域自适应以外，还有一些旨在通过深度神经网络进行特征学习的工作，例如Liu等人的最新工作[49]。

### C. 多模态迁移学习




















---
