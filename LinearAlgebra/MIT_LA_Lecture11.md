

[TOC]

# 0 说明

**笔记标题**：MIT_LA_Lecture11

**笔记版本**：v1.0

**对于文档的说明**：

1. 你可以在我的Github[仓库](https://github.com/agoclover/machine_learning/tree/master/Linear_algebra)中下载本笔记的Markdwon源文档，并通过浏览目录进行更方便高效地浏览；也欢迎在[知乎文章](https://zhuanlan.zhihu.com/p/76825461/)中进行浏览。
2. 本笔记参考的课程为MIT Linear Algebra（麻省理工线性代数），本课程在[网易公开课](http://open.163.com/special/opencourse/daishu.html)、[Bilibili](https://www.bilibili.com/video/av4042095)和[youtube](https://www.youtube.com/watch?v=ZK3O402wf1c&list=PLE7DDD91010BC51F8&index=1)等网站上都有视频资源，读者可以选择合适的平台观看。
3. 由于作者水平有限，笔记的内容、排版格式难免有不严谨的地方，希望读者能理解。

**对于内容的说明**：

1. 带箭头的小写字母表示的 $K^n$ 即 $n$ 维向量空间中的向量，比如 $\vec{a}$ ；用小写的 $\alpha,\beta,\gamma$ 等表示一般线性空间中的向量；用不带箭头的小写字母表示标量，比如 $a,b,c$。除非在特殊说明的情况下，有序数组的向量都表示的是列向量。用 $\vec a^T$ 来表示行向量。



# 11.1 矩阵空间

## 11.1.1 矩阵空间 

矩阵空间也是一个定义在数域 $K$ 上的线性空间：定义矩阵空间 $M$ 为 $s \times n$ 型矩阵构成的集合，矩阵之间存在加法运算和数乘运算，且仍得到 $s \times n$ 型矩阵。并且矩阵之间的加法运算和数乘运算满足线性空间定义的 8 条规律，所以矩阵空间是一个线性空间，矩阵空间的零元即 $s \times n$ 型零矩阵。

## 11.1.2 子空间

以所有定义在数域 $K$ 上的 $3 \times 3$ 矩阵构成的矩阵空间 $M$ 为例，它有以下这些很有意思的子空间：

### 对称矩阵空间

所有 $3 \times 3$ 的上三角矩阵构成的矩阵空间 $S$ 是 $M$ 的一个子空间，因为首先 $S$ 是 $M$ 的一个子集，并且两个对称矩阵相加仍是对称矩阵，对称矩阵乘一个数也仍是对称矩阵，即对 $M$ 的加法和乘法封闭，所以 $S$ 是 $M$ 的一个子空间。

### 上三角矩阵空间

所有 $3 \times 3$ 的对称矩阵构成的矩阵空间 $U$ 是 $M$ 的一个子空间，因为首先 $U$ 是 $M$ 的一个子集，并且两个上三角矩阵相加仍是上三角对称矩阵，上三角矩阵乘一个数也仍是上三角矩阵，即对 $M$ 的加法和乘法封闭，所以 $U$ 是 $M$ 的一个子空间。

## 11.1.3 矩阵空间的基和维数

### 一般矩阵空间

仍以所有定义在数域 $K$ 上的 $3 \times 3$ 矩阵构成的矩阵空间 $M$ 为例，它有一个包含 9 个向量的自然基：
$$
\left[
\begin{matrix}
1 & 0 & 0\\
0 & 0 & 0\\
0 & 0 & 0
\end{matrix}
\right],
\left[
\begin{matrix}
0 & 1 & 0\\
0 & 0 & 0\\
0 & 0 & 0
\end{matrix}
\right]
,\cdots,
\left[
\begin{matrix}
0 & 0 & 0\\
0 & 0 & 0\\
0 & 0 & 1
\end{matrix}
\right]
\tag{1}
$$
为什么它是一组基呢？我们在《线性代数-线性空间的知识梳理》中已经回顾过，**如果线性空间 $V$ 内的一个向量组线性无关且 $V$ 中所有向量都能由这个向量组线性表出，那么这个向量组是 $V$ 的一个基**。

而任意 $3 \times 3$ 矩阵都可以如下表示，且表法唯一：
$$
\left[
\begin{matrix}
a_{11} & a_{12} & a_{13}\\
a_{21} & a_{22} & a_{23}\\
a_{31} & a_{32} & a_{33}
\end{matrix}
\right]
=a_{11}
\left[
\begin{matrix}
1 & 0 & 0\\
0 & 0 & 0\\
0 & 0 & 0
\end{matrix}
\right]+\cdots+a_{33}
\left[
\begin{matrix}
0 & 0 & 0\\
0 & 0 & 0\\
0 & 0 & 1
\end{matrix}
\right]
\tag{2}
$$
所以（1）是 $M$ 的一个基，相应地 $dimM=9$ 。

当然这里并不是说（1）是唯一的一个基，还有无数其他基，我们只需要找出一个基就能确定线性空间的维数和结构了。

### 对称矩阵空间

仍以所有定义在数域 $K$ 上的 $3 \times 3$ 矩阵构成的矩阵空间 $M$ 为例，其对称矩阵子空间 $S$ 基和维数如何确定呢？

我们可以很容易得到以下 6 个向量构成 $S$ 的一个基：
$$
\left[
\begin{matrix}
1 & 0 & 0\\
0 & 0 & 0\\
0 & 0 & 0
\end{matrix}
\right],
\left[
\begin{matrix}
0 & 1 & 0\\
1 & 0 & 0\\
0 & 0 & 0
\end{matrix}
\right]
,
\left[
\begin{matrix}
0 & 0 & 1\\
0 & 0 & 0\\
1 & 0 & 0
\end{matrix}
\right]，
\left[
\begin{matrix}
0 & 0 & 0\\
0 & 1 & 0\\
0 & 0 & 0
\end{matrix}
\right]，
\left[
\begin{matrix}
0 & 0 & 0\\
0 & 0 & 1\\
0 & 1 & 0
\end{matrix}
\right]，
\left[
\begin{matrix}
0 & 0 & 0\\
0 & 0 & 0\\
0 & 0 & 1
\end{matrix}
\right]
\tag{3}
$$
因为这 6 个矩阵线性无关，且任意 $3 \times 3$ 对称矩阵都可以如下表示，且表法唯一：
$$
\left[
\begin{matrix}
a_{11} & a_{12} & a_{13}\\
a_{12} & a_{22} & a_{23}\\
a_{13} & a_{23} & a_{33}
\end{matrix}
\right]
=a_{11}
\left[
\begin{matrix}
1 & 0 & 0\\
0 & 0 & 0\\
0 & 0 & 0
\end{matrix}
\right]+
a_{12}
\left[
\begin{matrix}
0 & 1 & 0\\
1 & 0 & 0\\
0 & 0 & 0
\end{matrix}
\right]+
\cdots+a_{33}
\left[
\begin{matrix}
0 & 0 & 0\\
0 & 0 & 0\\
0 & 0 & 1
\end{matrix}
\right]
\tag{4}
$$
所以（3）是 $S$ 的一个基，相应地 $dimS=6$ 。

**同样我们强调， $S$ 的基不是只有这一个，但我们有一个基就够了，因为有一个基，基的维数就是子空间的维数，且子空间中所有向量都能由基唯一线性表出，就能研究这个子空间的结构了。**

### 上三角矩阵空间

仍以所有定义在数域 $K$ 上的 $3 \times 3$ 矩阵构成的矩阵空间 $M$ 为例，其上三角矩阵子空间 $U$ 基和维数如何确定呢？我们可以很容易得到以下 6 个向量构成 $U$ 的一个基：
$$
\left[
\begin{matrix}
1 & 0 & 0\\
0 & 0 & 0\\
0 & 0 & 0
\end{matrix}
\right],
\left[
\begin{matrix}
0 & 1 & 0\\
0 & 0 & 0\\
0 & 0 & 0
\end{matrix}
\right]
,
\left[
\begin{matrix}
0 & 0 & 1\\
0 & 0 & 0\\
1 & 0 & 0
\end{matrix}
\right]，
\left[
\begin{matrix}
0 & 0 & 0\\
0 & 1 & 0\\
0 & 0 & 0
\end{matrix}
\right]，
\left[
\begin{matrix}
0 & 0 & 0\\
0 & 0 & 1\\
0 & 0 & 0
\end{matrix}
\right]，
\left[
\begin{matrix}
0 & 0 & 0\\
0 & 0 & 0\\
0 & 0 & 1
\end{matrix}
\right]
\tag{5}
$$
所以 $dimU=6$。

## 11.1.4 子空间的交，和与维数定理

接下来到关键的地方了，建议先阅读《线性代数-线性空间的知识梳理》中子空间的**交**、**和**和**维数定理**等小节。

接下来我们研究矩阵空间 $M$ 的子空间 $S$ 和 $U$ 的交，即 $S \cap U$，这个比较简单，易知 $S \cap U$ 即对角矩阵，其维数明显为 3。

但若要直接研究 $S$ 与 $U$ 的和，即 $S+U$，这个就没有 $S \cap U$ 那么直观了：

**一种方法**是通过定义，即
$$
S+U=\{\alpha+\beta|\alpha\in S, \beta \in U\}
\tag{6}
$$
那么可以发现，对于任何一个 $3 \times 3$ 矩阵，它是可以表示成一个对称矩阵和一个上三角矩阵的和：
$$
\left[
\begin{matrix}
a_{11} & a_{12} & a_{13}\\
a_{21} & a_{22} & a_{23}\\
a_{31} & a_{32} & a_{33}
\end{matrix}
\right]
=
\left[
\begin{matrix}
a_{11} & a_{21} & a_{31}\\
a_{21} & a_{22} & a_{32}\\
a_{31} & a_{32} & a_{33}
\end{matrix}
\right]
+
\left[
\begin{matrix}
0 & a_{12}-a_{21} & a_{13}-a_{31}\\
0 & 0 & a_{23}-a_{32}\\
0 & 0 & 0
\end{matrix}
\right]
\tag{7}
$$
所以 $S+U=M$，因此 $dim(S+U)=9$。

**另一种方法**，为了确定 $S+U$ 的维数，可以利用维数定理，即
$$
dim(S+U)=dimS+dimU-dim(S\cap U)
\tag{8}
$$
这个公式中，$dim(S\cap U)=3,dim S=6,dim U=6$，所以 $dim (S+U)=9$，而由 $S+U$ 的定义可知，其本身就是 $M$ 的一个子空间，且 $dimM=9$，所以 $S+U=M$，即 $S$ 与 $U$ 的和刚好覆盖了整个矩阵空间 $M$。

这就是维数定理一个很好的应用，有时候直接分析两个子空间的和不容易，那么可以考虑通过维数定理先分别分析这两个子空间，再分析其交，这样就能得到 $dim(S+U)$，**一旦我们知道一个子空间的维数 $n$，那么只要找到这个子空间中 $n$ 个线性无关的向量，那么这 $n$ 个向量就是子空间的一个基**。

本小节除了介绍子空间的交，和和维数定理，另一方面是给出线性空间中元素一般性的例子，当然课堂中，老师还讲到了线性微分方程的解空间也是一个线性空间，这里不做具体介绍。



#11.2 秩 1 矩阵

对秩为 1 的矩阵，也可以进行研究，比如秩为 1 的矩阵
$$
A=
\left[
\begin{matrix}
1 & 4 & 5\\
2 & 8 & 10
\end{matrix}
\right]
\tag{9}
$$
我们从行向量的角度分解，可以等价表示为
$$
A=
\left[
\begin{matrix}
1 & 4 & 5\\
2 & 8 & 10
\end{matrix}
\right]
=
\left[
\begin{matrix}
1\\2
\end{matrix}
\right]
\left[
\begin{matrix}
1 & 4 & 5\\
\end{matrix}
\right]
\tag{10}
$$
我们有所有**秩为 1 的矩阵可以表示为一列乘以一行的形式**，即 $A=uv^T$。

之后的学习中，我们会认识到秩 1 矩阵行列式和特征值都会很简单。再讨论以下几个问题：

## 11.2.1 问题1

比如，一个 $s \times n$ 的矩阵的秩为 $r$，我们可以将其表示成 $r$ 个秩 1 矩阵的组合，所以秩 1 矩阵很有用，它就像搭建其他矩阵的积木一样。

举个简单例子
$$
A=
\left[
	\begin{matrix}
	1 & 2 & 2 & 2 \\
	2 & 4 & 6 & 8 \\
	3 & 6 & 8 & 10
	\end{matrix}
\right]=(\vec a_1,\vec a_2,\vec a_3,\vec a_4)
\tag{11}
$$
通过初等行变换
$$
A=
\left[
	\begin{matrix}
	1 & 2 & 2 & 2 \\
	2 & 4 & 6 & 8 \\
	3 & 6 & 8 & 10
	\end{matrix}
\right]
\sim
\left[
	\begin{matrix}
	1 & 2 & 2 & 2 \\
	0 & 0 & 2 & 4 \\
	0 & 0 & 0 & 0
	\end{matrix}
\right]
\sim
\left[
	\begin{matrix}
	1 & 2 & 0 & -2 \\
	0 & 0 & 1 & 2 \\
	0 & 0 & 0 & 0
	\end{matrix}
\right]
\tag{12}
$$
所以 $rankA=2$，$A$ 的 1 和 3 列是列空间的一个基，其零空间：
$$
N_{n×(n-r)}=
\left[
	\begin{matrix}
	-F_{r×(n-r)} \\
	I_{n-r} 
	\end{matrix}
\right]
=N_{4\times2}
=
\left[
	\begin{matrix}
	 -2& 2\\
	1& 0\\
  0 & -2\\
  0& 1\\
	\end{matrix}
\right]
\tag{13}
$$
由（11）第一列可知 $\vec a_2=2\vec a_1,\vec a_4=-2\vec a_1+2\vec a_3$，则
$$
A=(\vec a_1,2\vec a_1,\vec a_3,-2\vec a_1+2\vec a_3)=(\vec a_1,2\vec a_1,\vec 0,-2\vec a_1)+(\vec 0,\vec 0,\vec a_3,2\vec a_3)
\tag{14}
$$
 即
$$
A=\left[
	\begin{matrix}
	1 & 2 & 0 & -2 \\
	2 & 4 & 0 & -4 \\
	3 & 6 & 0 & -6
	\end{matrix}
\right]+
\left[
	\begin{matrix}
	0 & 0 & 2 & 4 \\
	0 & 0 & 6 & 12 \\
	0 & 0 & 8 & 16
	\end{matrix}
\right]
\tag{15}
$$
这就将 $A$ 分解成了两个秩 1 矩阵的和。

## 11.2.2 问题2

但 $s \times n$ 型矩阵所有秩 1 矩阵所构成的子集显然不是一个子空间。

## 11.2.3 问题3

我们来看这样一个定义在数域 $K$ 上的列向量的集合 $W$：
$$
\{[v_1,v_2,v_3,v_4]^T|v_1+v_2+v_3+v_4=0，v_1,v_2,v_3,v_4 \in K\}
\tag{16}
$$
它是 $K^4$ 的子空间吗？

我们很容易验证它对加法和数乘运算都封闭，所以 $W$ 是 $K^4$ 的一个子空间。

那么，这个子空间结构是什么样子，换句话说，它的基和维数又是什么？

观察到 $v_1+v_2+v_3+v_4=0$，这很像求解 $A\vec x=\vec0$ 时将化成的列向量组的形式，那么可以构造一个 $A=[1,1,1,1]$。这样，求 $W$ 的维数就变成了求 $A$ 的零空间的维数。而 $rank\space A=1$，所以 $rank\space N(A)=3$，即 $rank\space W=3$。同理，我们可以求出 $W$ 的一个基，即 $N(A)$ 的一个基为：
$$
N_{n×(n-r)}=
\left[
	\begin{matrix}
	-F_{r×(n-r)} \\
	I_{n-r} 
	\end{matrix}
\right]
=N_{4\times3}
=
\left[
	\begin{matrix}
	-1 & -1 & -1\\
	1  & 0  & 0\\
  0  & 1  & 0\\
  0  & 0  & 1
	\end{matrix}
\right]
\tag{17}
$$

------

