本笔记中，对矩阵元素经常使用“.”来代表省略，这并不表示这个位置元素为0，而是由于已在其他位置给出具有代表性的元素从而不再详细写出此元素。

# 1 方程组的几何解释

## 二元线性方程组

我们考虑以下二元方程组以及其矩阵形式$$Ax=b$$：
$$
4x-y=3\\ 2x+2y=4
$$

一般我们从**每一行**来认识这个方程，由于二元方程可以表示在XOY平面，我们可以画出(1)中两方程所表示的直线，我们也能很容易地求出满足以上方程的组合(x,y)=(1,1)，即图中的A点。

![image-20190716120908261](http://strawberryamoszc.oss-cn-shanghai.aliyuncs.com/2019-07-16-040908.png)

同时，我们也可以从每一列来理解这一方程组，即两向量的何种线性组合可以得到等号右端的向量：
$$
x\left[ \begin{matrix} 4 \\ 2 \end{matrix} \right] +y\left[ \begin{matrix} -1 \\ 2 \end{matrix} \right] =\left[ \begin{matrix} 3 \\ 4 \end{matrix} \right] \\ x\vec { w } +y\vec { v } =\vec { b } 
$$
我们也可以在XOY平面内画出$$\vec { w } $$和$$\vec { v } $$两向量，同理可以找出x=1，y=1：

![image-20190716124305728](http://strawberryamoszc.oss-cn-shanghai.aliyuncs.com/2019-07-16-044306.png)



## 多元线性方程组

我们将视角拉回多元情形，比如一般意义上的：
$$
{ A }_{ m\times n }{ \vec { x }  }_{ n\times 1 }={ \vec { b }  }_{ n\times 1 }\\ A=\left( { \vec { a }  }_{ 1 },{ \vec { a }  }_{ 2 },\quad ...{ \quad \vec { a }  }_{ n } \right) \\ \vec { x } ={ \left( { x }_{ 1 },{ x }_{ 2 },\quad ...\quad { x }_{ n } \right)  }^{ T }
$$
可以以列向量的线性表示的角度来看，即：
$$
{ x }_{ 1 }{ \vec { a }  }_{ 1 }+{ x }_{ 2 }{ \vec { a }  }_{ 2 }+...+{ x }_{ n }{ \vec { a }  }_{ n }=\vec { b } 
$$

## 矩阵列的线性组合

于是我们可以将方程组的几何解释理解为，在m维空间中，系数矩阵A的列向量，是否可以通过某组系数来线性表示为$$\vec { b } $$。线性方程组或矩阵方程看成**矩阵列的线性组合**是理解线性方程组、矩阵方程的很好的方式。

当然，是否存在这样的一组数据也就是等价于这个方程组是否有解，也可以从诸多角度来理解，这里不做过多解释。



# 2 矩阵消元

## 阶梯型矩阵

考虑以下线性方程组：
$$
x+2y+z=2\\ 3x+8y+z=12\\ 4y+z=2
$$
我们一般通过高斯消元法可以求解，即通过对其增广矩阵进行行变换来得到其**行阶梯型矩阵**：
$$
\left[ \begin{matrix} 1 & 2 & 1 \\ 3 & 8 & 1 \\ 0 & 4 & 1 \end{matrix} \right] \overset { { r }_{ 2 }-3{ r }_{ 1 } }{ \sim  } \left[ \begin{matrix} 1 & 2 & 1 \\ 0 & 2 & -2 \\ 0 & 4 & 1 \end{matrix} \right] \overset { { r }_{ 3 }-2{ r }_{ 2 } }{ \sim  } \left[ \begin{matrix} 1 & 2 & 1 \\ 0 & 2 & -2 \\ 0 & 0 & 5 \end{matrix} \right] 
$$

## 矩阵行的线性组合

在1中，我们将**矩阵乘列向量**理解为矩阵的列向量以列向量为系数进行线性表示，即**矩阵列的线性组合**(a combination of the columns of the matrix)。那么，如何理解矩阵的**行表示**呢？也就是如何来表示**行变换**呢：
$$
\left[ \begin{matrix} 1 & 2 & 3 \end{matrix} \right] \left[ \begin{matrix} 1\quad 2\quad 3\quad 4 \\ 2\quad 3\quad 4\quad 1 \\ 3\quad 4\quad 1\quad 2 \end{matrix} \right] =\left[ \begin{matrix} 1 & 2 & 3 \end{matrix} \right] \left[ \begin{matrix} { \vec { a }  }_{ 1 }^{ T } \\ { \vec { a }  }_{ 2 }^{ T } \\ { { \vec { a }  }_{ 3 }^{ T } } \end{matrix} \right] =1{ \vec { a }  }_{ 1 }^{ T }+2{ \vec { a }  }_{ 2 }^{ T }+3{ \vec { a }  }_{ 3 }^{ T }
$$
也就是说，我们可以将**行向量×矩阵**理解为矩阵的行向量以行向量为系数进行线性表示，即**矩阵行的线性组合**，最终得到一个4维行向量。那么更进一步地理解，多个行向量×矩阵也就可以表示如下，最终得到一个3×4的矩阵，即3个4维行向量：
$$
\left[ \begin{matrix} 1 & 2 & 3 \\ 2 & 3 & 1 \\ 3 & 1 & 2 \end{matrix} \right] \left[ \begin{matrix} 1\quad 2\quad 3\quad 4 \\ 2\quad 3\quad 4\quad 1 \\ 3\quad 4\quad 1\quad 2 \end{matrix} \right] =\left[ \begin{matrix} 1 & 2 & 3 \\ 2 & 3 & 1 \\ 3 & 1 & 2 \end{matrix} \right] \left[ \begin{matrix} { \vec { a }  }_{ 1 }^{ T } \\ { \vec { a }  }_{ 2 }^{ T } \\ { { \vec { a }  }_{ 3 }^{ T } } \end{matrix} \right] =\left[ \begin{matrix} 1{ \vec { a }  }_{ 1 }^{ T }+2{ \vec { a }  }_{ 2 }^{ T }+3{ \vec { a }  }_{ 3 } \\ 2{ \vec { a }  }_{ 1 }^{ T }+3{ \vec { a }  }_{ 2 }^{ T }+1{ \vec { a }  }_{ 3 } \\ 3{ \vec { a }  }_{ 1 }^{ T }+1{ \vec { a }  }_{ 2 }^{ T }+{ 2\vec { a }  }_{ 3 } \end{matrix} \right] 
$$

## 矩阵的初等变换

有了矩阵行表示之后，我们就可以很容易地理解(6)总矩阵的行变换，通过对矩阵左乘（右乘）可逆方阵来实现矩阵的行列变换，这就是矩阵的**初等变换**。

### 初等行变换

左乘初等矩阵可以实现矩阵的行变换。比如，我们是通过第2行-3倍的第1行得到(6)中间的矩阵，用矩阵变换也就是：
$$
\left[ \begin{matrix} 1 & 0 & 0 \\ -3 & 1 & 0 \\ 0 & 0 & 1 \end{matrix} \right] \left[ \begin{matrix} 1 & 2 & 1 \\ 3 & 8 & 1 \\ 0 & 4 & 1 \end{matrix} \right] =\left[ \begin{matrix} 1 & 2 & 1 \\ 0 & 2 & -2 \\ 0 & 4 & 1 \end{matrix} \right]
$$
在此基础上，我们是通过第3行-2倍的第2行得到(6)右边的矩阵，用矩阵变换也就是：
$$
\left[ \begin{matrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & -2 & 1 \end{matrix} \right] \left[ \begin{matrix} 1 & 0 & 0 \\ -3 & 1 & 0 \\ 0 & 0 & 1 \end{matrix} \right] \left[ \begin{matrix} 1 & 2 & 1 \\ 3 & 8 & 1 \\ 0 & 4 & 1 \end{matrix} \right] =\left[ \begin{matrix} 1 & 2 & 1 \\ 0 & 2 & -2 \\ 0 & 0 & 5 \end{matrix} \right]
$$
(10)也可以表示为$${ E }_{ 32 }\left( { E }_{ 21 }A \right) =U$$，虽然矩阵的顺序不能变，但矩阵计算具有**结合律**(associate law)，所以也可以写成$$\left( { E }_{ 32 }{ E }_{ 21 } \right) A=U$$，即A可以通过某种行变换一次性变为U。

### 初等列变换

右乘初等矩阵，也就是1中我们理解的那样，我们便可以实现矩阵的列变换。比如我们想交换两列的顺序：
$$
\left[ \begin{matrix} a & c \\ b & d \end{matrix} \right] \left[ \begin{matrix} 0 & 1 \\ 1 & 0 \end{matrix} \right] =\left[ \begin{matrix} c & a \\ d & b \end{matrix} \right] 
$$

# 3 矩阵乘法和逆

## 矩阵乘法的解释

我们考虑以下情况的矩阵乘法结果中的某一项$${ c }_{ 34 }$$：
$$
\left[ \begin{matrix} . & . & . \\ { a }_{ 31 } & { a }_{ 32 } & . \\ . & . & . \end{matrix} \right] \left[ \begin{matrix} . & { b }_{ 14 } & . \\ . & { b }_{ 24 } & . \\ . & . & . \end{matrix} \right] =\left[ \begin{matrix} . & . & . \\ . & { c }_{ 34 } & . \\ . & . & . \end{matrix} \right]
$$
我们有以下几种理解矩阵乘法的方式。

### 代数表达式

$${ c }_{ 34 }$$即A矩阵的第3行与B矩阵的第4列的点积：
$$
{ c }_{ 34 }=\left( row3\quad of\quad A \right) \cdot \left( col4\quad of\quad B \right) ={ a }_{ 31 }{ b }_{ 14 }+{ a }_{ 32 }{ b }_{ 24 }+...=\sum _{ k=1 }^{ n }{ { a }_{ 3k }{ b }_{ k4 } } 
$$

### A列向量的线性组合

在了解了初等变换后，我们可以将AB=C这个等式看做，矩阵A的各列向量通过乘B的各列来得到C的各列，即C的各列是矩阵A各列的线性组合。

Columns of C are the combinations of columns of A.
$$
\left[ \begin{matrix} { \vec { a }  }_{ 1 } & { { \vec { a }  }_{ 2 } } & { \vec { a }  }_{ 3 } \end{matrix} \right] \left[ \begin{matrix} \left[ \begin{matrix} { b }_{ 11 } \\ { b }_{ 21 } \\ { b }_{ 31 } \end{matrix} \right]  & \left[ \begin{matrix} . \\ . \\ . \end{matrix} \right]  & \left[ \begin{matrix} . \\ . \\ . \end{matrix} \right]  \end{matrix} \right] =\left[ \begin{matrix} { \vec { c }  }_{ 1 } & . & . \end{matrix} \right] 
$$

### B行向量的线性组合

我们还可以将AB=C这个等式看做，矩阵B的各行向量通过乘A的各行来得到C的各行，即C的各行是矩阵B的各行的线性组合。

Rows of C are the combinations of rows of B.
$$
\left[ \begin{matrix} \left[ \begin{matrix} { a }_{ 11 } & { a }_{ 12 } & { a }_{ 13 } \end{matrix} \right]  \\ \left[ \begin{matrix} . & . & . \end{matrix} \right]  \\ \left[ \begin{matrix} . & . & . \end{matrix} \right]  \end{matrix} \right] \left[ \begin{matrix} { \vec { b }  }_{ 1 }^{ T } \\ { \vec { b }  }_{ 2 }^{ T } \\ { \vec { b }  }_{ 3 }^{ T } \end{matrix} \right] =\left[ \begin{matrix} { \vec { c }  }_{ 1 }^{ T } \\ . \\ . \end{matrix} \right] 
$$

### A的列×B的行

$$
\left[ \begin{matrix} 2 \\ 3 \\ 4 \end{matrix} \right] \left[ \begin{matrix} 1 & 6 \end{matrix} \right] =\left[ \begin{matrix} 2\quad 12 \\ 3\quad 18 \\ 4\quad 24 \end{matrix} \right] 
$$

以上有两种理解方法，即左边这个列向量分别乘1和6得到右边这两个列向量，或右边这个行向量分别乘2，3，4得到右边3个行向量。而AB其实就是A和B分别以n进行列划分和行划分后，A的列和B的行的乘积的和：
$$
\left[ \begin{matrix} 2\quad 7 \\ 3\quad 8 \\ 4\quad 9 \end{matrix} \right] \left[ \begin{matrix} 1\quad 6 \\ 0\quad 0 \end{matrix} \right] =\left[ \begin{matrix} 2 \\ 3 \\ 4 \end{matrix} \right] \left[ 1\quad 6 \right] +\left[ \begin{matrix} 7 \\ 8 \\ 9 \end{matrix} \right] \left[ 0\quad 0 \right] =\left[ \begin{matrix} 2\quad 12 \\ 3\quad 18 \\ 4\quad 24 \end{matrix} \right] 
$$

### 分块矩阵

有时候，我们也可以通过对矩阵分块，得到一些为0矩阵或单位矩阵的项，使计算变得更加容易。以下给出了矩阵分块的一种划分，当然矩阵分块不一定局限于这种格式：
$$
\left[ \begin{matrix} { A }_{ 1 } & { A }_{ 2 } \\ { A }_{ 3 } & { A }_{ 4 } \end{matrix} \right] \left[ \begin{matrix} { B }_{ 1 } & { B }_{ 2 } \\ { B }_{ 3 } & { B }_{ 4 } \end{matrix} \right] =\left[ \begin{matrix} { A }_{ 1 }{ B }_{ 1 }+{ A }_{ 2 }{ B }_{ 2 } & . \\ . & . \end{matrix} \right] 
$$

## 逆矩阵

对于方阵A，如果有$${ A }^{ -1 }A=A{ A }^{ -1 }=I$$，则称A是可逆矩阵(invertible)或非奇异矩阵(non-sigular)，反之则称方阵A为不可逆矩阵或奇异矩阵。

### 如何理解或判定矩阵是否可逆

#### 行列式是否为0

如果$$\left| A \right| =0$$，则A不可逆，反之可逆。

#### 秩是否为n

如果$$rank\left( A \right) =n$$，则A可逆，否则A不可逆。

#### 列向量是否线性相关

以列向量分析，在n维空间内，如果列向量线性相关，即线性无关的列向量个数小于n，比如是k，那么由这n个列向量表示出的向量一定在k维平面内，而等式右端的I各列共有n维向量，所以I无法由这些列向量线性表出，即不存在与A相乘积为I的矩阵。

#### Ax=0

如果能找到一个非零向量$$\vec{x}$$，使得$$A\vec { x } =\vec { 0 } $$成立，则A不可逆。因为如果$${ A }^{ -1 }$$存在，将其左乘于等式，便能得到$$\vec { x } =\vec { 0 } $$，这与非零向量的假设矛盾了。

### 求逆矩阵

#### Gauss-Jordan elimination

求逆矩阵的本质是同时对n个方程组进行高斯消元或进行初等变换。我们可以通过对其增广矩阵进行行变换，使A变为I，与此同时原本的I就变成了$${A}^{-1}$$，其原理如下：
$$
{ E }_{ n }{ ... }{ E }_{ 2 }{ E }_{ 1 }A=I={ A }^{ -1 }A\\ { E }_{ n }{ ... }{ E }_{ 2 }{ E }_{ 1 }I={ E }_{ n }{ ... }{ E }_{ 2 }{ E }_{ 1 }={ A }^{ -1 }
$$
