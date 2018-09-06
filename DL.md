# Introduction to Deep Learning

1. 线性分类，交叉熵
2. 随机梯度下降，使用一个sample梯度下降，快，但是注意learningrate的选择
3. 添加动量梯度下降，避免梯度下降震荡，可以正负抵消一部分，加快收敛
4. 极大似然估计，一组联合概率，已知模型分布，求参数。  
5. 交叉熵：-sum(ylogP +(1-y)log(1-P))，越小越好。
多分类交叉熵：∑ ∑ [ yij ln(Pij) ] ( i = 1, 2, 3 ... n ) ( j = 1, 2, 3 ...m ) 
6. 卷积层中的参数数量是 K*F*F*D_in + K，深度 K, height、width，：
padding=same，height=ceil(H_in/stride);padding=valid,height=ceil((H_in-F+1)/s))
7. 最大池化层，可以减小图片不同位置出现的影响。有没有一种superviseCNN，
利用已经训练好的树木花草，对图片中不相干进行剔除
8. 权重初始化，全0、1，效果非常差。均匀分布，取值范围在正负之间好于只去正数。
一般取1/sqrt(n)，n为输入数量。正态分布，截断正态分布更好，一般取值mean=0，std=1/sqrt(n)。
9. bias，直观是让sigmoid更灵活，调整峰值之类的