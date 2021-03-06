## 矩阵逆的物理意义

一个矩阵如果其逆存在，则它的行列式不为零（这里只讨论方阵）。

行列式不为零，则说明不存在任意两行（或两列）成等比例关系。

这样，就可以把矩阵的每一行（或列）看作是一个基（或说轴），对比正交坐标系来理解。

想象一下，有一个正交坐标系$E$摆在那儿不动，把矩阵$A$中的每一行（或列）看成是一个向量，它在$E$中表出就是一条过原点的射线(反向延伸至无穷远处即成一轴)，因为$A$可逆，所以这样的射线正好有$n$条，它们有可能:

- 相互垂直，类似于$E$中的各坐标轴一样，但不等于$E$
- 部分轴垂直，其它的不垂直
- 所有的轴都不垂直（想象点光原，发射出$n$条射线的一束光，是很easy的事）
- 完全等于$E$

对于这$n$条射线上的单位刻度（只考虑$2$范数模长度量）有可能:

- 和$E$上的单位$1$相等
- 各轴相等，但和$E$不相等
- 各轴都不一

以上种种可能，几乎囊括了任意一个$n$阶可逆阵$A$。若把$A$看作一个如上分析的**坐标系**，同样$B=A^{-1}$，可被看作是另一个**坐标系**。

如果把左乘矩阵看作是一个**"运动"**操作，则
$$
BA=A^{-1}A=E
$$

表示坐标系$A$经过$B$**运动**，被还原成了正交坐标系$E$， 显然，摆在那儿的原正交坐标系$E$的各个轴，经过一系列的拉伸掰扯，一定是能拉成$A$坐标系的。而**$A$经过一系列反向操作（B运动）**， 也是一定能够还原成$E$的。

于是**矩阵逆**的一种物理意义至少可以理解为：

- <font color=blue>反向掰扯拉压坐标轴（基）使之还原成标准正交坐标系$E$</font>


另外，如果$B$是$A$的逆，根据定义它们是满足交换性质的：
$$
BA=AB=AA^{-1}=E
$$

左乘矩阵的**运动**等价于一系列的**行初等变换**集体作用效果，就是把$A$中的每一行看作基进行变换操作。

右乘矩阵等价于一系列的**列初等变换**集体作用效果，$AB=E$就可看作是把$A$中的每一列当成坐标轴，经过一系列的拉伸掰扯，使之成为正交坐标系$E$

### 总结
综上分析，除第一种物理意义理解方式明了之外，好像还不能概括**逆**的所有物理意义， 所以我就用**玄**一点方法来理解～：

**逆**就是两个“掰歪”了的坐标系$A$和$B$，它们经过**乘**相互作用，**韶（$sh\grave{a}o$,四声）**的一下就变成了正交直角坐标系$E$，且这种神奇的相互作用是可交换的。

### 参考
- [理解矩阵（一）](https://blog.csdn.net/myan/article/details/647511)
- [理解矩阵（二）](https://blog.csdn.net/myan/article/details/649018)
- [理解矩阵（三）](https://blog.csdn.net/myan/article/details/1865397)
