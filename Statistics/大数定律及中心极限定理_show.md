# 大数定律及中心极限定理

在数学与统计学中, 大数定律又称大数法则, 大数律, 是描述相当多次数重复实验的结果的定律. 根据这个定律知道, 样本数量越多, 则随机变量或其统计量的算术平均值就有越高的概率接近期望值. 

大数定律很重要, 因为它 "说明" 了一些随机事件的均值的长期稳定性. 人们发现, 在重复试验中, 随着试验次数的增加, 事件发生的频率趋于一个稳定值；人们同时也发现, 在对物理量的测量实践中, 测定值的算术平均也具有稳定性. 比如, 我们向上抛一枚硬币, 硬币落下后哪一面朝上是偶然的, 但当我们上抛硬币的次数足够多后, 达到上万次甚至几十万几百万次以后, 我们就会发现, 硬币每一面向上的次数约占总次数的二分之一, 亦即偶然之中包含着必然. 

上述现象是**切比雪夫不等式**的一个特殊应用情况, **辛钦定理**和**伯努利大数定律**也都概括了这一现象, 它们统称为大数定律. 

## 举例

例如, 抛掷一颗均匀的6面的骰子, 1, 2, 3, 4, 5, 6应等概率出现, 所以每次扔出骰子后, 出现点数的期望值是  ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%7B%5Cfrac%20%7B1%2B2%2B3%2B4%2B5%2B6%7D%7B6%7D%7D%3D3.5%7D) .

根据大数定理, 如果多次抛掷骰子, 随着抛掷次数的增加, 平均值 (样本平均值) 应该接近3.5, 根据大数定理, 在多次伯努利实验中, 实验概率最后收敛于理论推断的概率值, 对于伯努利随机变量, 理论推断的成功概率就是期望值, 而若对 n 个相互独立的随机变量的平均值, 频率越多则相对越精准. 

例如硬币投掷即伯努利实验, 当投掷一枚均匀的硬币, 理论上得出的正面向上的概率应是1/2. 因此, 根据大数定理, 正面朝上的比例在相对 "大" 的数字下,  "理应" 接近为1/2, 尤其是正面朝上的概率在n次实验 (n接近无限大时) 后应几近收敛到1/2. 

即使正面朝上 (或背面朝上) 的比例接近1/2, 几乎很自然的正面与负面朝上的绝对差值 (absolute difference差值范围) 应该相应随着抛掷次数的增加而增加. 换句话说, 绝对差值的概率应该是会随着抛掷次数而接近于0. 直观的来看, 绝对差值的期望会增加, 只是慢于抛掷次数增加的速度. 

<img src="../pics/大数定律举例.png" alt="大数定律举例" style="zoom:33%;" />

如上, 以特定掷单个骰子的过程来展示大数定律. 随着投掷次数的增加, 所有结果的均值趋于3.5 (骰子点数的期望值) . 不同时候做的这个实验会在投掷次数较小的时候 (左部) 会表现出不同的形状, 当次数变得很大 (右部) 的时候, 它们将会非常相似. 

## 表现形式

大数定律主要有两种表现形式: 弱大数定律和强大数定律. 定律的两种形式都肯定无疑地表明, 样本均值  ![math](https://render.githubusercontent.com/render/math?math=%7B%5Coverline%20%7BX%7D%7D_%7Bn%7D%3D%7B%5Cfrac%20%7B1%7D%7Bn%7D%7D%28X_%7B1%7D%2B%5Ccdots%20%2BX_%7Bn%7D%29)  收敛于真值  ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%7B%5Coverline%20%7BX%7D%7D_%7Bn%7D%5Cto%20%5Cmu%20%5Cquad%20%7B%5Ctextrm%20%7Bas%7D%7D%5Cquad%20n%5Cto%20%5Cinfty%20%7D) .

其中  ![math](https://render.githubusercontent.com/render/math?math=X_1%2C%20X_2) , ... 是独立同分布, 期望值  ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%5Coperatorname%20%7BE%7D%20%28X_%7B1%7D%29%3D%5Coperatorname%20%7BE%7D%20%28X_%7B2%7D%29%3D%5C%2C%5Ccdots%20%5C%2C%3D%5Cmu%20%7D)  且皆勒贝格可积的随机变量构成的无穷序列.  ![math](https://render.githubusercontent.com/render/math?math=X_j)  的勒贝格可积性意味着期望值  ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%5Coperatorname%20%7BE%7D%20%28X_%7Bj%7D%29%7D)  存在且有限. 

方差  ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%5Coperatorname%20%7BVar%7D%20%28X_%7B1%7D%29%3D%5Coperatorname%20%7BVar%7D%20%28X_%7B2%7D%29%3D%5C%2C%5Ccdots%20%5C%2C%3D%5Csigma%20%5E%7B2%7D%3C%5Cinfty%20%7D)  有限的假设是非必要的. 很大或者无穷大的方差会使其收敛得缓慢一些, 但大数定律仍然成立. 通常采用这个假设来使证明更加简洁. 

强和弱之间的差别在所断言的收敛的方式. 对于这些方式的解释, 参见随机变量的收敛. 

### 弱大数定律

弱大数定律也称为**辛钦定理**, 陈述为: 样本均值依概率收敛于期望值. 



![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%7B%5Coverline%20%7BX%7D%7D_%7Bn%7D%5C%20%7B%5Cxrightarrow%20%7BP%7D%7D%5C%20%5Cmu%20%5Cquad%20%7B%5Ctextrm%20%7Bas%7D%7D%5Cquad%20n%5Cto%20%5Cinfty%20%7D)



也就是说对于任意正数 ε,



![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%5Clim%20_%7Bn%5Cto%20%5Cinfty%20%7DP%5Cleft%28%5C%2C%7C%7B%5Coverline%20%7BX%7D%7D_%7Bn%7D-%5Cmu%20%7C%3E%5Cvarepsilon%20%5C%2C%5Cright%29%3D0%7D)



### 强大数定律

强大数定律指出, 样本均值以概率 1 收敛于期望值. 



![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%7B%5Coverline%20%7BX%7D%7D_%7Bn%7D%5C%20%7B%5Cxrightarrow%20%7B%5Ctext%7Ba.s.%7D%7D%7D%5C%20%5Cmu%20%5Cquad%20%7B%5Ctextrm%20%7Bas%7D%7D%5Cquad%20n%5Cto%20%5Cinfty%20%7D)


即



![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20P%5Cleft%28%5Clim%20_%7Bn%5Cto%20%5Cinfty%20%7D%7B%5Coverline%20%7BX%7D%7D_%7Bn%7D%3D%5Cmu%20%5Cright%29%3D1%7D)



#### 切比雪夫定理的特殊情况

设 ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20a_%7B1%7D%2C%5C%20a_%7B2%7D%2C%5C%20%5Cdots%20%5C%20%2C%5C%20a_%7Bn%7D%2C%5C%20%5Cdots%20%7D)  为相互独立的随机变量, 其数学期望为:  ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%5Coperatorname%20%7BE%7D%20%28a_%7Bi%7D%29%3D%5Cmu%20%5Cquad%20%28i%3D1%2C%5C%202%2C%5C%20%5Cdots%20%29%7D) , 方差为:  ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%5Coperatorname%20%7BVar%7D%20%28a_%7Bi%7D%29%3D%5Csigma%20%5E%7B2%7D%5Cquad%20%28i%3D1%2C%5C%202%2C%5C%20%5Cdots%20%29%7D) 

则序列  ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%7B%5Coverline%20%7Ba%7D%7D%3D%7B%5Cfrac%20%7B1%7D%7Bn%7D%7D%5Csum%20_%7Bi%3D1%7D%5E%7Bn%7Da_%7Bi%7D%7D) 依概率收敛于  ![math](https://render.githubusercontent.com/render/math?math=%5Cmu)   (即收敛于此数列的数学期望  ![math](https://render.githubusercontent.com/render/math?math=E%28a_%7Bi%7D%29) ) . 

换言之, 在定理条件下, 当 n 无限变大时, n 个随机变量的算术平均将变成一个常数. 

#### 伯努利大数定律

设在 n 次独立重复伯努利试验中, 事件  ![math](https://render.githubusercontent.com/render/math?math=X)  发生的次数为  ![math](https://render.githubusercontent.com/render/math?math=n_%7Bx%7D) , 事件  ![math](https://render.githubusercontent.com/render/math?math=X)  在每次试验中发生的总体概率为  ![math](https://render.githubusercontent.com/render/math?math=p) ,  ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%7B%5Cfrac%20%7Bn_%7Bx%7D%7D%7Bn%7D%7D%7D)  代表样本发生事件  ![math](https://render.githubusercontent.com/render/math?math=X)  的频率. 

则对任意正数  ![math](https://render.githubusercontent.com/render/math?math=%5Cvarepsilon%20%3E0)  , 伯努利大数定律表明: 



![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%5Clim%20_%7Bn%5Cto%20%5Cinfty%20%7D%7BP%7B%5Cleft%5C%7B%5Cleft%7C%7B%5Cfrac%20%7Bn_%7Bx%7D%7D%7Bn%7D%7D-p%5Cright%7C%3C%5Cvarepsilon%20%5Cright%5C%7D%7D%7D%3D1%7D)



换言之, 事件发生的频率依概率收敛于事件的总体概率. 该定理以严格的数学形式表达了频率的稳定性, 也就是说当 n 很大时, 事件发生的频率于总体概率有较大偏差的可能性很小. 


# 中心极限定理


## 总体分布服从正态分布


任意一个样本, 无论样本容量多大, 样本均值的抽样分布都服从正态分布. 


## 总体不服从正态分布


只要样本容量足够 

![math](https://render.githubusercontent.com/render/math?math=n%3E30)

, 即使总体不服从正态分布, 样本均值的抽样分布也会近似服从正态分布. 
