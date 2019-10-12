
## 总体框架  

#### 基于多模态输入特征所提出的多层注意力网络的框图  

![img](../imgs/fe993184-e1d0-11e9-81b4-2a2ae2dbcce4.png)  

每个模态上的关注层，训练网络去注意模态内最重要的特征，以创建该模态的上下文特征。

每个模态的上下文特征都通过两层前馈网络传递，并且这3个前馈网络的输出融合在另一个堆叠的BLSTM中。

3个前馈网络的输出包含每个模态最重要的功能，并融合在一起以形成另一个连接向量，并在其上面有一个关注层。

该关注层的输出乘以堆叠的Bi-LSTM输出的输出，并通过回归器。向后传播回归器的损失，以训练在网络的每个级别上学习到的权重，从而确保端到端的训练。

---
## Dataset

The Extended Distress Analysis Interview Corpus dataset (E-DAIC)——扩展疾病分析访谈语料库数据集

来自[The Distress Analysis Interview Corpus of human and computer interviews](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.495.3966&rep=rep1&type=pdf)

分为四种类型：
- Face-to-face（面对面）
- Teleconference（电话会议）
- Wizard-of-Oz（动画人物，由人控制）
- Automated（动画人物，不由人控制）



---

## 研究方法

### 1、单一模态分别训练模型

- #### 1.1 Text
 - 数据集：[AVEC 2019 Workshop and Challenge: State-of-Mind, Detecting Depression with AI, and Cross-Cultural Affect Recognition](https://arxiv.org/pdf/1907.11510.pdf)

 - 使用[Universal Sentence Encoder(通用句子编码器)](https://arxiv.org/pdf/1803.11175.pdf)获取句子嵌入

 - 使用两层堆叠式双向长期短期记忆网络架构，其中句子嵌入作为输入， 身体健康问卷抑郁量表(PHQ)得分作为输出，来训练语音转录的回归模型

 - 每个BLSTM层都有200个隐藏单元，其中第一BLSTM层的前向隐藏层的每个隐藏单元的输出连接到第二层的前向隐藏单元的输入

- #### 1.2 Audio

- #### 1.3 Visual

### 2、Fusion
