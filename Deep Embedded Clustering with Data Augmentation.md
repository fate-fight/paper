# 使用数据增强来进行深度嵌入聚类   

由于深度嵌入聚类能更好的提取数据的特征，能够更好的对数据进行表示，因此先对数据使用神经网络进行特征提取后进行聚类的效果已经大大超过了传统的聚类方法。<br/>  
本文在原来深度嵌入聚类的基础上使用数据增强来训练网络，增加了训练集，可以更好的训练模型。<br/>

<div align=center><img height=250 src="https://github.com/fate-fight/paper/blob/master/images/DECDA.png"></div>

DEC模型的原理是使用一个编码器来表示数据的特征，也就是数据降维，为了训练编码器能够更好的表示数据，这里使用了一个解码器对特征层进行解码，使得解码后的结果能够逼近原数据，那么就可以证明这个编码器有效，因此使用一个Reconstruction Loss来训练编码器，同时将数据进行编码后使用聚类工具进行聚类是有一个聚类损失，两者之和就是数据的Loss Function，之后用这个损失函数训练模型。<br/>
<div align=center><img height=250 src="https://github.com/fate-fight/paper/blob/master/images/DECDAA.png"></div>

DECDA模型，首先使用数据增强的数据来训练AE模块，并产生输出，初始化聚类中心，聚类值和目标向量t，之后固定t,使用数据增强的数据来训练AE，然后固定编码器和输出层权重，来更新t的值，直到误差满足要求后停止。Loss Function为重建损失和聚类损失之和。

