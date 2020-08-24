# 随机变量数字特征

# 期望

如果  ![math](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle%20X)  是在概率空间 ![math](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle%20%28%5COmega%20%2CF%2CP%29) 中的[随机变量](https://zh.wikipedia.org/wiki/%E9%9A%8F%E6%9C%BA%E5%8F%98%E9%87%8F), 那么它的期望值  ![math](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle%20%5Coperatorname%20%7BE%7D%20%28X%29)  的定义是:  ![math](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle%20%5Coperatorname%20%7BE%7D%20%28X%29%3D%5Cint%20%7B%5COmega%20%7DX%5C%2C%5Cmathrm%20%7Bd%7D%20P) , 并不是每一个随机变量都有期望值的, 因为有的时候上述积分不存在. 


如果两个随机变量的分布相同, 则它们的期望值也相同. 


如果  ![math](https://render.githubusercontent.com/render/math?math=X)  是**离散**的随机变量, 输出值为 ![math](https://render.githubusercontent.com/render/math?math=x_%7B1%7D%2Cx_%7B2%7D%2C%5Cldots) , 和输出值相应的概率为  ![math](https://render.githubusercontent.com/render/math?math=p_%7B1%7D%2Cp_%7B2%7D%2C%5Cldots)  (概率和为1). 


若**级数**  ![math](https://render.githubusercontent.com/render/math?math=%5Csum%20_%7Bi%7Dp_%7Bi%7Dx_%7Bi%7D)  [绝对收敛](https://zh.wikipedia.org/wiki/%E7%BB%9D%E5%AF%B9%E6%94%B6%E6%95%9B), 那么期望值  ![math](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle%20%5Coperatorname%20%7BE%7D%20%28X%29)  是一个无限数列的和:  ![math](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle%20%5Coperatorname%20%7BE%7D%20%28X%29%3D%5Csum%20_%7Bi%7Dp_%7Bi%7Dx_%7Bi%7D) .


如果  ![math](https://render.githubusercontent.com/render/math?math=X)  是**连续**的随机变量, 存在一个相应的[概率密度函数](https://zh.wikipedia.org/wiki/%E6%A6%82%E7%8E%87%E5%AF%86%E5%BA%A6%E5%87%BD%E6%95%B0)  ![math](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle%20f%28x%29) , 若**积分**  ![math](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle%20%5Cint%20_%7B-%5Cinfty%20%7D%5E%7B%5Cinfty%20%7Dxf%28x%29%5C%2C%5Cmathrm%20%7Bd%7D%20x)  绝对收敛, 那么  ![math](https://render.githubusercontent.com/render/math?math=X)  的期望值可以计算为: 




![math](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle%20%5Coperatorname%20%7BE%7D%20%28X%29%3D%5Cint%20_%7B-%5Cinfty%20%7D%5E%7B%5Cinfty%20%7Dxf%28x%29%5C%2C%5Cmathrm%20%7Bd%7D%20x)




是针对于连续的随机变量的, 与离散随机变量的期望值的算法同出一辙, 由于输出值是连续的, 所以把求和改成了积分. 


# 方差
## 定义

方差 (Variance) , 应用数学里的专有名词. 在概率论和统计学中, 一个随机变量的方差描述的是它的离散程度, 也就是该变量离其期望值的距离. 这里把复杂说白了, 就是各个误差将之平方 (而非取绝对值, 使之肯定为正数) , 相加之后再除以总数, 透过这样的方式来算出各个数据分布、零散 (相对中心点) 的程度. 继续延伸的话, 方差的正平方根称为该随机变量的标准差 (此为相对各个数据点间) . 


设  ![math](https://render.githubusercontent.com/render/math?math=X)  为服从分布  ![math](https://render.githubusercontent.com/render/math?math=F)  的随机变量,  如果  ![math](https://render.githubusercontent.com/render/math?math=E%5BX%5D)  是随机变量  ![math](https://render.githubusercontent.com/render/math?math=X)  的期望值.  随机变量  ![math](https://render.githubusercontent.com/render/math?math=X)  或者分布  ![math](https://render.githubusercontent.com/render/math?math=F)  的**方差**为 (均值 ![math](https://render.githubusercontent.com/render/math?math=%5Cmu%3DE%5BX%5D) ): 




![math](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle%20%5Coperatorname%20%7BVar%7D%20%28X%29%3D%5Coperatorname%20%7BE%7D%20%5Cleft%5B%28X-%5Cmu%20%29%5E%7B2%7D%5Cright%5D)




这个定义涵盖了连续、离散、或两者都有的随机变数. 方差亦可当作是随机变数与自己本身的共变异数(或协方差): 




![math](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle%20%5Coperatorname%20%7BVar%7D%20%28X%29%3D%5Coperatorname%20%7BCov%7D%20%28X%2CX%29)




## 离散随机变量的方差

如果随机变数X是具有机率质量函数的离散机率分布  ![math](https://render.githubusercontent.com/render/math?math=x_1%20%5Crightarrow%20p_1%2C%20...%2C%20x_n%20%5Crightarrow%20p_n) , 则: 




![math](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle%20%5Coperatorname%7BVar%7D%28X%29%20%3D%20%5Csum_%7Bi%3D1%7D%5En%20p_i%5Ccdot%28x_i%20-%20%5Cmu%29%5E2%20%3D%20%5Csum_%7Bi%3D1%7D%5En%20%28p_i%5Ccdot%20x_i%5E2%29%20-%20%5Cmu%5E2)




 ![math](https://render.githubusercontent.com/render/math?math=%5Cmu)  是其期望值:  ![math](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle%20%5Cmu%20%3D%5Csum%20_%7Bi%3D1%7D%5E%7Bn%7Dp_%7Bi%7D%5Ccdot%20x_%7Bi%7D) 


## 连续随机变量的方差

如果随机变量  ![math](https://render.githubusercontent.com/render/math?math=X)  是连续分布, 并对应至概率密度函数  ![math](https://render.githubusercontent.com/render/math?math=f%28x%29) , 则其方差为: 


 ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%5Coperatorname%20%7BVar%7D%20%28X%29%3D%5Csigma%20%5E%7B2%7D%3D%5Cint%20%28x-%5Cmu%20%29%5E%7B2%7D%5C%2Cf%28x%29%5C%2Cdx%5C%2C%3D%5Cint%20x%5E%7B2%7D%5C%2Cf%28x%29%5C%2Cdx%5C%2C-%5Cmu%20%5E%7B2%7D%7D) 


 ![math](https://render.githubusercontent.com/render/math?math=%5Cmu)  是其期望值:  ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%5Cmu%20%3D%5Cint%20x%5C%2Cf%28x%29%5C%2Cdx%5C%2C%7D) 


> [1] [wikipedia/方差](https://zh.wikipedia.org/wiki/%E6%96%B9%E5%B7%AE)

# 标准差
## 定义

标准差 (又称标准偏差、均方差, 英语: Standard Deviation, 缩写SD) , 数学符号  ![math](https://render.githubusercontent.com/render/math?math=%5Csigma)  (sigma) , 在概率统计中最常使用作为测量一组数值的离散程度之用. 标准差定义: 为方差开算术平方根, 反映组内个体间的离散程度；标准差与期望值之比为标准离差率. 测量到分布程度的结果, 原则上具有两种性质: 


- 为非负数值 (因为开平方后再做平方根) ；
- 与测量资料具有相同单位 (这样才能比对) . 


**一个总体的标准差或一个随机变量的标准差, 及一个子集合样本数的标准差之间, 有所差别**.

## 总体标准差



![math](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle%20SD%3D%20%5Csqrt%7B%5Cfrac%7B1%7D%7BN%7D%20%5Csum_%7Bi%3D1%7D%5EN%20%28x_i%20-%20%5Cmu%29%5E2%7D)



上述公式可以如下代换而简化: 




![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%0A%7B%5Cbegin%7Baligned%7D%5Csum%20_%7Bi%3D1%7D%5E%7BN%7D%28X_%7Bi%7D-%5Cmu%20%29%5E%7B2%7D%26%3D%7B%7D%5Csum%20%0A_%7Bi%3D1%7D%5E%7BN%7D%28X_%7Bi%7D%5E%7B2%7D-2X_%7Bi%7D%5Cmu%20%2B%5Cmu%20%5E%7B2%7D%29%5C%5C%26%7B%7D%3D%5Cleft%28%5Csum%20%0A_%7Bi%3D1%7D%5E%7BN%7DX_%7Bi%7D%5E%7B2%7D%5Cright%29-%5Cleft%282%5Cmu%20%5Csum%20_%7Bi%3D1%7D%5E%7BN%7DX_%7Bi%7D%5Cright%29%2BN%5Cmu%20%0A%5E%7B2%7D%5C%5C%26%7B%7D%3D%5Cleft%28%5Csum%20_%7Bi%3D1%7D%5E%7BN%7DX_%7Bi%7D%5E%7B2%7D%5Cright%29-2%5Cmu%20%28N%5Cmu%20%29%2BN%5Cmu%20%0A%5E%7B2%7D%5C%5C%26%7B%7D%3D%5Cleft%28%5Csum%20_%7Bi%3D1%7D%5E%7BN%7DX_%7Bi%7D%5E%7B2%7D%5Cright%29-2N%5Cmu%20%5E%7B2%7D%2BN%5Cmu%20%0A%5E%7B2%7D%5C%5C%26%7B%7D%3D%5Cleft%28%5Csum%20_%7Bi%3D1%7D%5E%7BN%7DX_%7Bi%7D%5E%7B2%7D%5Cright%29-N%5Cmu%20%0A%5E%7B2%7D%5Cend%7Baligned%7D%7D%7D)




所以: 




![math](https://render.githubusercontent.com/render/math?math=%5Cbegin%7Barray%7D%7Bc%7D%0A%5Csigma%20%3D%20%7B%5Csqrt%20%7B%7B%5Cfrac%20%7B1%7D%7BN%7D%7D%5Csum%20_%7Bi%20%3D%201%7D%5E%7BN%7D%28X_%7Bi%7D-%5Cmu%20%29%5E%7B2%7D%7D%7D%20%3D%20%5Csqrt%7B%5Cfrac%7B1%7D%7BN%7D%20%5Cleft%28%5Csum_%7Bi%20%3D%201%7D%5EN%20X_i%5E2%5Cright%29%20-%20%5Cfrac%7B1%7D%7BN%7DN%5Cmu%5E2%7D%20%3D%20%7B%5Csqrt%20%7B%7B%5Cfrac%20%7B1%7D%7BN%7D%7D%5Cleft%28%5Csum%20_%7Bi%20%3D%201%7D%5E%7BN%7DX_%7Bi%7D%5E%7B2%7D%5Cright%29-%7B%5Cfrac%20%7B1%7D%7BN%7D%7DN%5Cmu%20%5E%7B2%7D%7D%7D%0A%5Cend%7Barray%7D)




根号里面, 亦即变异数  ![math](https://render.githubusercontent.com/render/math?math=%5Csigma%5E2)  的简易口诀为: **平方和的平均**减去**平均的平方**. 


> [1] [https://zh.wikipedia.org/wiki/標準差](https://zh.wikipedia.org/wiki/%E6%A8%99%E6%BA%96%E5%B7%AE)

# 协方差 Covariance
## 定义

协方差表示的是两个变量的总体的误差, 这与只表示一个变量误差的方差不同.  如果两个变量的变化趋势一致, 也就是说如果其中一个大于自身的期望值, 另外一个也大于自身的期望值, 那么两个变量之间的协方差就是正值.  如果两个变量的变化趋势相反, 即其中一个大于自身的期望值, 另外一个却小于自身的期望值, 那么两个变量之间的协方差就是负值.  



![math](https://render.githubusercontent.com/render/math?math=Cov%28X%2CY%29%3DE%5B%28X-EX%29%28Y-EY%29%5D)



可以通俗的理解为: **两个变量在变化过程中是同方向变化？还是反方向变化？同向或反向程度如何？**

- 你变大, 同时我也变大, 说明两个变量是同向变化的, 这时协方差就是正的；
- 你变大, 同时我变小, 说明两个变量是反向变化的, 这时协方差就是负的；
- 从数值来看, 协方差的数值越大, 两个变量同向程度也就越大, 反之亦然. 


## 性质

如果  ![math](https://render.githubusercontent.com/render/math?math=X)  与  ![math](https://render.githubusercontent.com/render/math?math=Y)  是实数随机变量,  ![math](https://render.githubusercontent.com/render/math?math=a)  与  ![math](https://render.githubusercontent.com/render/math?math=b)  是常数, 那么根据协方差的定义可以得到以下性质: 



![math](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle%20%5Coperatorname%20%7Bcov%7D%20%28X%2CX%29%3D%5Coperatorname%20%7Bvar%7D%20%28X%29)




![math](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle%20%5Coperatorname%20%7Bcov%7D%20%28X%2CY%29%3D%5Coperatorname%20%7Bcov%7D%20%28Y%2CX%29)




![math](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle%20%5Coperatorname%20%7Bcov%7D%20%28aX%2CbY%29%3Dab%5C%2C%5Coperatorname%20%7Bcov%7D%20%28X%2CY%29)



对于随机变量序列  ![math](https://render.githubusercontent.com/render/math?math=X_1%2C...%2CX_n)  与  ![math](https://render.githubusercontent.com/render/math?math=Y_1%2C...%2CY_m) , 有
                       


![math](https://render.githubusercontent.com/render/math?math=%5Cbegin%7Barray%7D%7Bc%7D%0A%5Cdisplaystyle%20%0A%5Coperatorname%20%7Bcov%7D%20%5Cleft%28%5Csum%20_%7Bi%3D1%7D%5E%7Bn%7D%7BX_%7Bi%7D%7D%2C%5Csum%20%0A_%7Bj%3D1%7D%5E%7Bm%7D%7BY_%7Bj%7D%7D%5Cright%29%3D%5Csum%20_%7Bi%3D1%7D%5E%7Bn%7D%7B%5Csum%20_%7Bj%3D1%7D%5E%7Bm%7D%7B%5Coperatorname%20%0A%7Bcov%7D%20%5Cleft%28X_%7Bi%7D%2CY_%7Bj%7D%5Cright%29%7D%7D%0A%5Cend%7Barray%7D)



对于随机变量序列  ![math](https://render.githubusercontent.com/render/math?math=X_1%2C...%2CX_n) , 有



![math](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle%20%0A%5Coperatorname%20%7Bvar%7D%20%5Cleft%28%5Csum%20_%7Bi%3D1%7D%5E%7Bn%7DX_%7Bi%7D%5Cright%29%3D%5Csum%20%0A_%7Bi%3D1%7D%5E%7Bn%7D%5Coperatorname%20%7Bvar%7D%20%28X_%7Bi%7D%29%2B2%5Csum%20%0A_%7Bi%2Cj%5C%2C%3A%5C%2Ci%3Cj%7D%5Coperatorname%20%7Bcov%7D%20%28X_%7Bi%7D%2CX_%7Bj%7D%29)




# 相关系数


在概率论和统计学中, 相关 (Correlation) , 显示两个随机变量之间线性关系的强度和方向. 在统计学中, 相关的意义是用来衡量两个变量相对于其相互独立的距离. 在这个广义的定义下, 有许多根据数据特点而定义的用来衡量数据相关的系数.  


## 皮尔逊积矩相关系数 Pearson's


相关性的度量有很多种, 这里介绍一种最常用的皮尔逊积矩相关系数. 在统计学中, **皮尔逊积矩相关系数** (英語: Pearson product-moment correlation coefficient, 又称作 **PPMCC**或**PCCs**, 文章中常用r或Pearson's r表示) 用于度量两个变量X和Y之间的[相关](https://zh.wikipedia.org/wiki/%E7%9B%B8%E5%85%B3)程度 (线性相关) , 其值介于-1与1之间. 在自然科学领域中, 该系数广泛用于度量两个变量之间的线性相关程度. 它是由卡尔·皮尔逊从弗朗西斯·高尔顿在19世纪80年代提出的一个相似却又稍有不同的想法演变而来. 这个相关系数也称作“皮尔森相关系数r”. 


pearson 描述的是线性相关关系, 取值 [-1, 1]. 负数表示负相关, 正数表示正相关. 在显著性的前提下, 绝对值越大, 相关性越强. 绝对值为0,  无线性关系；绝对值为1表示完全线性相关. 


相关系数也可以看成协方差: 一种剔除了两个变量量纲影响、标准化后的特殊协方差. 既然是一种特殊的协方差, 那它: 


1. 也可以反映两个变量变化时是同向还是反向, 如果同向变化就为正, 反向变化就为负. 
2. 由于它是标准化后的协方差, 因此更重要的特性来了: 它消除了两个变量变化幅度的影响, 而只是单纯反应两个变量每单位变化时的相似程度. 



### 总体相关系数


两个变量之间的皮尔逊相关系数定义为两个变量之间的[协方差](https://zh.wikipedia.org/wiki/%E5%8D%8F%E6%96%B9%E5%B7%AE)和[标准差](https://zh.wikipedia.org/wiki/%E6%A0%87%E5%87%86%E5%B7%AE)的商: 



![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%5Crho_%7BX%2CY%7D%20%3D%5Cfrac%7Bcov%28X%2CY%29%7D%7B%5Csigma%20_%7BX%7D%5Csigma%20_%7BY%7D%7D%3D%20%5Cfrac%7BE%5B%28X-%5Cmu%20%0A_%7BX%7D%29%28Y-%5Cmu%20_%7BY%7D%29%5D%7D%7B%5Csigma%20_%7BX%7D%5Csigma%20_%7BY%7D%7D%20%7D)




上式定义了总体相关系数, 常用希腊小写字母  ![math](https://render.githubusercontent.com/render/math?math=%5Crho)  作为代表符号. 


### 样本相关系数


估算样本的协方差和标准差, 可得到样本相关系数(样本皮尔逊系数), 常用英文小写字母  ![math](https://render.githubusercontent.com/render/math?math=r)  代表: 



![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20r%20%3D%20%5Cfrac%7B%5Csum_%7Bi%3D1%7D%5E%7Bn%7D%20%5Cleft%20%28%20X_%7Bi%7D-%5Cbar%7BX%7D%20%5Cright%20%29%20%20%5Cleft%20%28%20Y_%7Bi%7D-%5Cbar%7BY%7D%20%5Cright%20%29%20%20%7D%0A%7B%5Csqrt%7B%20%5Csum_%7Bi%3D1%7D%5E%7Bn%7D%20%5Cleft%20%28%20X_%7Bi%7D-%5Cbar%7BX%7D%20%5Cright%20%29%5E2%20%7D%5Csqrt%7B%5Csum_%7Bi%3D1%7D%5E%7Bn%7D%20%5Cleft%20%28%20Y_%7Bi%7D-%5Cbar%7BY%7D%20%5Cright%20%29%5E2%7D%20%20%7D%7D)




 ![math](https://render.githubusercontent.com/render/math?math=r)  亦可由 ![math](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle%20%28X_%7Bi%7D%2CY_%7Bi%7D%29)  样本点的标准分数均值估算, 得到与上式等价的表达式: 



![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20r%20%3D%20%5Cfrac%7B1%7D%7Bn-1%7D%5Csum_%7Bi%3D1%7D%5E%7Bn%7D%20%20%5Cleft%20%28%20%5Cfrac%7BX_%7Bi%7D-%5Cbar%7BX%7D%7D%7B%5Csigma_%7BX%7D%7D%20%20%5Cright%20%29%20%5Cleft%20%28%20%5Cfrac%7BY_%7Bi%7D-%5Cbar%7BY%7D%7D%7B%5Csigma_%7BY%7D%7D%20%20%5Cright%20%29%20%7D)




其中 ![math](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle%20%7B%5Cfrac%20%7BX_%7Bi%7D-%7B%5Coverline%20%7BX%7D%7D%7D%7B%5Csigma%20_%7BX%7D%7D%7D) 、  ![math](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle%20%7B%5Coverline%20%7BX%7D%7D)  及  ![math](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle%20%5Csigma%20_%7BX%7D)  分别是  ![math](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle%20X_%7Bi%7D)  样本的标准分数、样本平均值和样本标准差. 


> [1] [https://zh.wikipedia.org/wiki/皮尔逊积矩相关系数](https://zh.wikipedia.org/wiki/%E7%9A%AE%E5%B0%94%E9%80%8A%E7%A7%AF%E7%9F%A9%E7%9B%B8%E5%85%B3%E7%B3%BB%E6%95%B0)
> [2] [https://www.zhihu.com/question/20852004/answer/134902061]()



## 斯皮尔曼等级相关系数 Spearman's


衡量单调关系 (无论是线性的还是非线性的) 的标准, Spearman系数适用于连续和离散变量, 包括序数变量 (Ordinal variable) . 


> [1] [https://zh.wikipedia.org/wiki/斯皮尔曼等级相关系数](https://zh.wikipedia.org/wiki/%E6%96%AF%E7%9A%AE%E5%B0%94%E6%9B%BC%E7%AD%89%E7%BA%A7%E7%9B%B8%E5%85%B3%E7%B3%BB%E6%95%B0)



## Kendall 等级相关系数


是用于测量两个测量量之间的序数关联的统计量. 与Spearman相关性相反, Kendall相关性不受彼此等级之间的距离的影响, 而仅受观察之间的等级是否相等的影响, 因此仅适用于离散变量但不适用于连续变量. 


# 矩和协方差矩阵
