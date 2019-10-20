# Stand-Alone Self-Attention in Vision Models  
   本文主要是想要研究自注意力网络能否单独处理图像，而不是只是在卷积上的增强，为此提出了将注意力作为一个单独的模块来处理视觉模型。
<div align=center><img height=300 src="https://github.com/fate-fight/paper/blob/master/images/sa_alone.png"></div>

模型的原理是先将特征图做三次1 * 1卷积，获得query，keys，value图，然后让卷积中心的query乘卷积核的大小的周围k * k的区域，得到的结果做一下softmax，然后和value图相乘后的结果相加得到目标点的值。
