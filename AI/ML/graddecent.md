# 梯度下降算法

![grad](grad.gif ':size=400*247')

很多时候，人们喜欢拿这张图来展示不同的**梯度下降算法**， 当然没错，直观，漂亮！

但不管什么样的变种，诸如$SGD, MM, NAG, Adagrad, Adadelta, Rmsprop...$统统都离不开**梯度**这一最本质的东西！

所以下面，只以最直白的方式扯扯**梯度**的哲学思想， 哲学？嗯，没错！就是**哲学**～～

所谓**梯度**也叫**导数**，导数的意义是什么？

**回忆一下：** 

对于一元函数，如果某一点的导数大于零，说明在该点附近函数是单调递增的，此时您如果沿该点往**左**走**一点点**函数值会上升，
往**右**走**一点点**函数值会下降，哈哈，有了这个**哲学**方向性的指导，问题就好办了，好办了，根据您的需求：

- 求**最（更）大值**？就往**右**走（梯度上升）
- 求**最（更）小值**？就往**左**走（梯度下降）

那一步走多少呢？就是所谓的学习率$\eta$。走完一步后，再计算当前的导数（**梯度**）用以指导下一步应该是继续往前走还是回撤一点。

直到给定的**"抬腿"**次数达到上限（累了～）或说已经找到了需求目标（导数为零了，下一步往哪个方向走都是错） **停止**。

以上就是**梯度**的本质，哲学指导了方向啊，所以说**方向**很重要，同志们～

而各种变种算法都是在研究这个**步子**， 怎么走？

- 步子大点，嘿，容易“扯蛋”，来回瞎折腾；步子小点儿，太慢，太磨叽了...... 
- 匀速前进，呆瓜一个
- 加速前进，什么时候刹车呀？嘟...嘟...刹不住了，老大...
- 变速前进，咱因地制宜，该快就快，该慢就慢好吧，嗯，小伙子想法不错！ 走...,耶...耶...爷...地形太复杂（代码太长了？），这么高频的时快时慢，老子晕车啊，“瞎走”一天......清醒过来后问，这是到哪儿啦？平谷？珠峰？海底世界？还TM在原地呢......
- ......


得， **走路**真**TM**是一门学问呐......,慢慢体会吧，您内!