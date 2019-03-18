## 如何理解矩阵与坐标的对应关系

<font color=blue>假设在某空间中随手画一条直线，若说它的坐标是$(3,4)$，则其长度为$5$。</font>

如何理解这句**简单**的描述？

其实这句话隐含了很多默认，它至少包括

- 是拿一个**直角**坐标系在**衡量**该线
- 让直角坐标系的原点$(0,0)$对应于直线的某一端，则另一端的坐标是$(3,4)$
- 该坐标系上的**单位刻度**，与拿米尺量得其长度为**$5$**的**单位刻度**，是一样的

若画成图，人们一般会习惯性的忽略以上诸多默认，得到如下的简单印象。

<div align=center><img src="AI/DL/1.jpg", width=500, height=309></div>

<font color=red>空间上随手划就的一条长度为$5$的直线$l$，它是一个**固定**不变的物理存在!</font>

我们说它的坐标是$(3,4)$，实则是说拿了上面那样一个$xy$**坐标系** *量了*一下，得到它的坐标是$(3,4)$。

现一步步拆开来看。

假设$l$在二维空间中可用向量$\overrightarrow{v}=(a,b)$来描述，则它在$xy$**坐标系**中与矩阵的对应关系为:

$$
\left [ \begin{array}{c} x \\ y \end{array}\right ] = 
\left [ \begin{array}{c} 1 & 0 \\
0 & 1 \end{array}\right] 
\left [ \begin{array}{c} a \\ b \end{array}\right ] 
= \left [ \begin{array}{c} 3 \\ 4 \end{array}\right ]
$$

该**直角坐标系**就可以理解为矩阵
$$
A=\left [ \begin{array}{c} 1 & 0 \\
0 & 1 \end{array}\right] 
$$
其第一行表示$x$轴的单位度量，第二行表示$y$轴的单位度量，就是常说的**基**。
向量$\overrightarrow{v}$在第一个基上的投影是$3$，第二个基上的投影是$4$，所以得到$a,b$分别是$3,4$。（参考[内积的物理意义](https://blog.csdn.net/dcrmg/article/details/52416832)理解）

从矩阵的角度看它是个单位阵$E$，由此也可窥矩阵中常用的单位阵$E$所表示的几何意义：
- 它的每一行代表一个轴
- 每个轴的单位度量都是**一**
- 每两个轴之间都互相垂直（三维可想象）

现如果把$x$轴逆时针旋转$\theta_{1}$，$y$轴逆时针转$\theta_{2}$，得到一个**新坐标系$O(x'y')$**, 如图：
<div align=center><img src="AI/DL/2.jpg", width=500, height=309></div>

新坐标系中的两个轴和矩阵就变为：

$$
A'=\left [ \begin{array}{c} \cos\theta_{1} & \sin\theta_{1} \\
\sin\theta_{2} & \cos\theta_{2} \end{array}\right]
$$

在新坐标系中的坐标也相应的变为：
$$
\left [ \begin{array}{c} x' \\ y' \end{array}\right ] =
\left [ \begin{array}{c} \cos\theta_{1} & \sin\theta_{1} \\
\sin\theta_{2} & \cos\theta_{2} \end{array}\right]
\left [ \begin{array}{c} a \\ b \end{array}\right ]
=\left [ \begin{array}{c} \cos\theta_{1} & \sin\theta_{1} \\
\sin\theta_{2} & \cos\theta_{2} \end{array}\right]
 \left [ \begin{array}{c} 3 \\ 4 \end{array}\right ]
=
\left [ \begin{array}{c} 3\cos\theta_{1} + 4\sin\theta_{1} \\
3\sin\theta_{2} + 4\cos\theta_{2} \end{array}\right]
$$

由$\theta_{1},\theta_{2}$的任意性，可知同一物理量在不同的坐标系下有不同的度量，它分别与不同的**矩阵**一一对应了。

只要$x'$与$y'$不重叠，都是两个维度在对其度量。对应到矩阵就是$|A'|$(行列式值)不为零，若为零，则说明第一个基与第二个基相应值成等比例关系，即共线（重叠）了，它会少了一个维度的刻画，这也是我们经常见到术语中要求矩阵的**行列式**不为零（或说满秩）的几何意义。

### 再看度量：

如果$x'$轴上是**两个单位长度**等价于量它所用米尺的**一个单位长度**("米尺量其为$5$")，
$y'$轴上是**叁个单位长度**等价于量它的米尺的**一个单位长度**，则
$$
A'=\left [ \begin{array}{c} 2\cos\theta_{1} & 2\sin\theta_{1} \\
3\sin\theta_{2} & 3\cos\theta_{2} \end{array}\right]
$$
意指$x'$轴上的数值是两个单位长度等价于一，$y'$轴上的数值是叁个单位长度等价于一。
由$\theta_{1},\theta_{2}$和伸缩度量（$2$和$3$）的任意性，可知$A'$有无数种变形。也即意味着你随手写一个矩阵，只要其行列式值不为零，它就是一个可以用来度量$l$的**坐标系**。

### 更进一步：
如果用三维来度量$l$，就得用$3 \times 3$矩阵来刻画它，若再考虑$l$还有一些其它的属性，则用$n \times n$矩阵，都同样适合上面的分析。

### 总结
由上分析可知：
- 若见到任意一个行列式不为零的**矩阵**，都可把它看作是一个坐标系
- 如果说某一$n$维向量是$(x_{1},x_{2},...x_{n})$，一般都是默认指它在$n$阶单位阵$E$下的坐标是$(x_{1},x_{2},...x_{n})$ 
- 它在新坐标系下的坐标$(x_{1}',x_{2}',...x_{n}')$，就是**新坐标系**对应的矩阵$A'$与原坐标的乘
	- $$\left[ \begin{array}{c} x_{1}' \\ x_{2}'\\...\\x_{n}' \end{array} \right ]=\left [ \begin{array}{c} a_{11} & a_{12},&...& a_{1n}\\ a_{21} & a_{22} &... &a_{2n}\\...&...&...\\a_{n1} &a_{n2}&...&a_{nn}\end{array}\right]\left[ \begin{array}{c} x_{1} \\ x_{2}\\...\\x_{n} \end{array} \right ] $$