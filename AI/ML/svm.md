# Support vector macheine (支持向量机)





## 升维

假设有$x_1,x_2,...x_d$, $d$个属性特征向量，每一个取值范围都是$x_i \in R$。 

- **线性关系：**

$ Y =W[1,X]^T=w_0*1+\sum_{i=1}^{d}w_i*x_i$

$W$ 有$1+d$个**基**， 分别是{$1, x_1, x_2,...x_d$}

- **非线性关系：**

$ \phi (x) = [1,x_1,x_2...,x_d, x_1^2, x_1x_2,x_1x_3,...x_1x_d...x_d^2, x_1^3...x_d^3]^T$

若以最高次不超过三次的多项式为**基**， 则它至多包含$1+d+d^2+d^3$维（有部分重复， 如$x_1x_2, x_2x_1, x_1x_2x_3,x_2x_3x_1...$）等！

然后$Y=W\phi(X)$中，$W$的维数就变成更高维了。

在更高维空间上，处理的方法用的仍是线性关系的方法，而它的输入数据只有$d$维。

这样就在更高维空间中用线性关系，模拟了低维空间里的**非线性关系**


