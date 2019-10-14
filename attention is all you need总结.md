# Attention is All You Need

   谷歌于2017发布的这篇文章提出了一种全新的模型结构来处理机器翻译问题，没有使用常用的的循环神经网络和卷积神经网络，而使用一种Transformer的结构主要原理是注意力机制，整体架构也是使用经典的Encoder-Decoder结构，Transformer结构大大减少了训练的时间，并取得了star of art的效果
* ## 模型的整体结构
<div align=center><img src="https://github.com/fate-fight/paper/blob/master/images/transformer.png"></div>

* ## Encoder部分
   Enconder的基本单元主要是Multi-Head Attention和feed-forward，中间存在残差连接以及层归一化
