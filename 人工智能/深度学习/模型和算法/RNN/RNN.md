# RNN
程豪

## 原理

RNN的原理参考[^1]，不再赘述。

## 代码实现

本部分参考pytorch的官方文档[^2]。

在pytorch中提供了`torch.nn.RNN`这一网络层。

输入要求`(seq_len, batch, input_size)`，但如果指定了`batch_first=True`，那么输入要求就是`(batch, seq_len, input_size)`。关于这一点可以参考[^3]。

经过该层之后的输出结果是`(seq_len, batch, num_directions * hidden_size)`。

举例：输入是`(batch_size,feature)`，经过一层嵌入层后`(batch_size,feature,embed_size)`，此即可作为该层的输入。





[^1]: 零基础入门深度学习(5) - 循环神经网络，https://zybuluo.com/hanbingtao/note/541458，讲解详细。
[^2]:https://pytorch.org/docs/master/generated/torch.nn.RNN.html，pytorch官方文档。
[^3]:读PyTorch源码学习RNN（1） - 得嘞您内的文章 - 知乎 https://zhuanlan.zhihu.com/p/32103001。解释了`batch_first`的原因