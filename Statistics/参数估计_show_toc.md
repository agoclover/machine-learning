<a name="index">**Contents**</a>

<a href="#0">参数估计</a>  
&emsp;<a href="#1">导读</a>  
&emsp;<a href="#2">点估计</a>  
&emsp;&emsp;<a href="#3">矩估计</a>  
&emsp;&emsp;<a href="#4">极大似然估计</a>  
&emsp;&emsp;<a href="#5">估计量的评选标准</a>  
&emsp;<a href="#6">区间估计</a>  
&emsp;&emsp;<a href="#7">基本思路</a>  
# <a name="0">参数估计</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

## <a name="1">导读</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

**点估计**就是用一个数据 (data) 的函数 (通常称为估计统计量, estimator) 来给出一个未知参数的估计值. 


即使是固定的参数真值 (虽然我们不知道这个值) , 由于数据的随机性, 不同的数据代入这个函数往往会得出不同的估计值 (estimation ) . 所以我们往往在点估计的基础上包裹上一个邻域, 即得到一个**区间估计**. 


那么点估计周围的这个邻域的大小是怎么确定的呢？一个最直接的答案就是: 确定一个百分比, p%, 使得给定任意数据集, 参数的估计值 (estimation) 落在这个邻域内的概率为p%. 那么, 确定邻域大小的问题就变成了确定**参数估计量** (estimator) 的分布的问题了. 


首先, 如果我们假设总体服从**正态分布**. 那么可以证明, 统计量作为随机变量的函数, 往往会服从从正态分布中推导出来的一系列分布 (如 t 分布, chi-square分布和F分布) , 那么通过统计量 (estimator) 的分布, 我们可以很轻松的得到所求邻域的大小. 


但是, 在日常生活中, 数据并不一定服从正态分布的. 如果总体不是正态分布的, 那么估计统计量 (estimator) 很可能也不服从正态分布, t 分布, chi-square 分布和 F 分布这些我们已知的分布. 如果我们不知道统计量的分布, 就无法确定应该给这个点估计包裹一个多大的邻域. 


于是我们退而求其次, 由于在满足一定正则条件的情况下, 很多数据的分布都会在数据量趋近于无穷的情况下趋近于正态分布. 比如, **中心极限定理** (Central Limit Theorem, 以下简称 CLT) 说的是样本均值的极限分布为正态分布. 而估计量一般可以表示成样本均值的函数 (e.g. OLS, GMM) ,  所以知道了样本均值的极限 (正态) 分布也就知道了这些估计量的极限分布. 于是我们就可以计算区间估计中的置信区间了. 


最后, 如果正则条件不满足, CLT 无法适用. 数据分布即使在数据量趋于无穷的情况下仍然不是正态分布, 这时候, 采用传统方法得到区间估计的办法就行不通了. 需要采用更加先进的方法 (比如 bootstrapping 寻找区间估计; 比如彻底抛弃 parametric model 转用 semi- non-parametric model 等等) . 


其实 CLT 不单单在找区间估计的时候用到. 很多**假设检验**的问题都依赖于统计量 (或者数据等) 的分布是正态分布这一假设. 所以如果假设统计量本身就是正态的, 那么当然可以以这些统计量为基础进行假设检验. 但是如果分布不是正态的, 那很有可能就需要 CLT 来帮助 (至少建立在极限状态下的正态性) 证明假设检验 (包括区间估计) 的正当性: 因为如果统计量不是正态的, 那么得出来的东西根本对不上号, 假设检验也就没啥大意义了. 


## <a name="2">点估计</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


### <a name="3">矩估计</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


在统计学中, 矩估计 (英语: method of moments) 是估计总体参数的方法. 首先推导涉及感兴趣的参数的总体矩 (即所考虑的随机变量的幂的期望值) 的方程. 然后取出一个样本并从这个样本估计总体矩. 接着使用样本矩取代 (未知的) 总体矩, 解出感兴趣的参数. 从而得到那些参数的估计. 矩估计是英国统计学家卡尔·皮尔逊于1894年提出的. 


假设问题是要估计表征随机变量  ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20W%7D)  的分布  ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20f_%7BW%7D%28w%3B%5Ctheta%20%29%7D)  的  ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20k%7D)  个未知参数 ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%5Ctheta%20_%7B1%7D%2C%5Ctheta%20_%7B2%7D%2C%5Cdots%20%2C%5Ctheta%20_%7Bk%7D%7D) . 如果真实分布 ("总体矩") 的前  ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20k%7D)  阶矩可以表示成这些  ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%5Ctheta%20%7D)  的函数:

 ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%5Cmu%20_%7B1%7D%5Cequiv%20E%5BW%5D%3Dg_%7B1%7D%28%5Ctheta%20_%7B1%7D%2C%5Ctheta%20_%7B2%7D%2C%5Cdots%20%2C%5Ctheta%20_%7Bk%7D%29%2C%7D) 

 ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%5Cmu%20_%7B2%7D%5Cequiv%20E%5BW%5E%7B2%7D%5D%3Dg_%7B2%7D%28%5Ctheta%20_%7B1%7D%2C%5Ctheta%20_%7B2%7D%2C%5Cdots%20%2C%5Ctheta%20_%7Bk%7D%29%2C%7D) 

 ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%5Cvdots%20%7D) 

 ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%5Cmu%20_%7Bk%7D%5Cequiv%20E%5BW%5E%7Bk%7D%5D%3Dg_%7Bk%7D%28%5Ctheta%20_%7B1%7D%2C%5Ctheta%20_%7B2%7D%2C%5Cdots%20%2C%5Ctheta%20_%7Bk%7D%29.%7D) 

设取出一大小为  ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20n%7D)  的样本, 得到  ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20w_%7B1%7D%2C%5Cdots%20%2Cw_%7Bn%7D%7D) . 对于  ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20j%3D1%2C%5Cdots%20%2Ck%7D) , 令




![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%7B%5Chat%20%7B%5Cmu%20%7D%7D_%7Bj%7D%3D%7B%5Cfrac%20%7B1%7D%7Bn%7D%7D%5Csum%20_%7Bi%3D1%7D%5E%7Bn%7Dw_%7Bi%7D%5E%7Bj%7D%7D)




为 j 阶样本矩, 是  ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%5Cmu%20_%7Bj%7D%7D)  的估计.  ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%5Ctheta%20_%7B1%7D%2C%5Ctheta%20_%7B2%7D%2C%5Cdots%20%2C%5Ctheta%20_%7Bk%7D%7D)  的矩估计量记为  ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%7B%5Chat%20%7B%5Ctheta%20%7D%7D_%7B1%7D%2C%7B%5Chat%20%7B%5Ctheta%20%7D%7D_%7B2%7D%2C%5Cdots%20%2C%7B%5Chat%20%7B%5Ctheta%20%7D%7D_%7Bk%7D%7D) , 由这些方程的解 (如果存在) 定义: 

 ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%7B%5Chat%20%7B%5Cmu%20%7D%7D_%7B1%7D%3Dg_%7B1%7D%28%7B%5Chat%20%7B%5Ctheta%20%7D%7D_%7B1%7D%2C%7B%5Chat%20%7B%5Ctheta%20%7D%7D_%7B2%7D%2C%5Cdots%20%2C%7B%5Chat%20%7B%5Ctheta%20%7D%7D_%7Bk%7D%29%2C%7D) 

 ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%7B%5Chat%20%7B%5Cmu%20%7D%7D_%7B2%7D%3Dg_%7B2%7D%28%7B%5Chat%20%7B%5Ctheta%20%7D%7D_%7B1%7D%2C%7B%5Chat%20%7B%5Ctheta%20%7D%7D_%7B2%7D%2C%5Cdots%20%2C%7B%5Chat%20%7B%5Ctheta%20%7D%7D_%7Bk%7D%29%2C%7D) 

 ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%7B%5Chat%20%7B%5Cmu%20%7D%7D_%7Bk%7D%3Dg_%7Bk%7D%28%7B%5Chat%20%7B%5Ctheta%20%7D%7D_%7B1%7D%2C%7B%5Chat%20%7B%5Ctheta%20%7D%7D_%7B2%7D%2C%5Cdots%20%2C%7B%5Chat%20%7B%5Ctheta%20%7D%7D_%7Bk%7D%29.%7D) 




### <a name="4">极大似然估计</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>
在统计学中, 最大似然估计 (英语: maximum likelihood estimation, 缩写为MLE) , 也称极大似然估计、最大概似估计, 是用来估计一个概率模型的参数的一种方法. 


给定一个概率分布 D, 已知其概率密度函数 (连续分布) 或概率质量函数 (离散分布) 为  ![math](https://render.githubusercontent.com/render/math?math=f_D) , 以及一个分布参数  ![math](https://render.githubusercontent.com/render/math?math=%5Ctheta)  , 我们可以从这个分布中抽出一个具有 n 个值的采样  ![math](https://render.githubusercontent.com/render/math?math=X_1%2C%20X_2%2C%5Cldots%2C%20X_n) , 利用  ![math](https://render.githubusercontent.com/render/math?math=f_D)  计算出其似然函数: 


 ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20%7B%5Cmbox%7BL%7D%7D%28%5Ctheta%20%5Cmid%20x_%7B1%7D%2C%5Cdots%20%2Cx_%7Bn%7D%29%3Df_%7B%5Ctheta%20%7D%28x_%7B1%7D%2C%5Cdots%20%2Cx_%7Bn%7D%29.%7D) 


若 D 是离散分布,  ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20f_%7B%5Ctheta%20%7D%7D)  即是在参数为  ![math](https://render.githubusercontent.com/render/math?math=%5Ctheta)  时观测到这一采样的概率. 若其是连续分布,  ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cdisplaystyle%20f_%7B%5Ctheta%20%7D%7D)  则为  ![math](https://render.githubusercontent.com/render/math?math=X_1%2C%20X_2%2C%5Cldots%2C%20X_n)  联合分布的概率密度函数在观测值处的取值. 一旦我们获得  ![math](https://render.githubusercontent.com/render/math?math=X_1%2C%20X_2%2C%5Cldots%2C%20X_n) , 我们就能求得一个关于  ![math](https://render.githubusercontent.com/render/math?math=%5Ctheta)  的估计. 最大似然估计会寻找关于  ![math](https://render.githubusercontent.com/render/math?math=%5Ctheta)  的最可能的值 (即, 在所有可能的  ![math](https://render.githubusercontent.com/render/math?math=%5Ctheta)  取值中, 寻找一个值使这个采样的“可能性”最大化) . 从数学上来说, 我们可以在 ![math](https://render.githubusercontent.com/render/math?math=%5Ctheta)  的所有可能取值中寻找一个值使得似然函数取到最大值. 这个使可能性最大的  ![math](https://render.githubusercontent.com/render/math?math=%5Cwidehat%7B%5Ctheta%7D)  值即称为  ![math](https://render.githubusercontent.com/render/math?math=%5Ctheta)  的最大似然估计. 由定义, 最大似然估计是样本的函数. 


### <a name="5">估计量的评选标准</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


无偏性, 有效性, 相合性.


## <a name="6">区间估计</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


### <a name="7">基本思路</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


1. 如果已知总体分布为正态分布, 那么从抽样分布一节我们知道, 其某些样本统计量满足正态分布, 卡方分布,  ![math](https://render.githubusercontent.com/render/math?math=t)  分布和  ![math](https://render.githubusercontent.com/render/math?math=F)  分布. 
2. 知道样本统计量的分布对我们来说是非常有帮助的, 即使在我们不知道分布参数的情况下. 比如我们知道了总体  ![math](https://render.githubusercontent.com/render/math?math=X%5Csim%20N%5Cleft%28%20%5Cmu%20%2C%7B%20%5Csigma%20%20%7D%5E%7B%202%20%7D%20%5Cright%29) , 那么样本均值  ![math](https://render.githubusercontent.com/render/math?math=%5Cbar%20%7B%20X%20%7D%20%5Csim%20N%5Cleft%28%20%5Cmu%20%2C%5Cfrac%20%7B%20%7B%20%5Csigma%20%20%7D%5E%7B%202%20%7D%20%7D%7B%20n%20%7D%20%20%5Cright%29) , 如果我们知道  ![math](https://render.githubusercontent.com/render/math?math=%5Csigma)  和  ![math](https://render.githubusercontent.com/render/math?math=n) , 那么只有一个未知参数  ![math](https://render.githubusercontent.com/render/math?math=%5Cmu)  不知道, 这个  ![math](https://render.githubusercontent.com/render/math?math=%5Cmu)  也是我们要估计的未知参数. 
3. 由  ![math](https://render.githubusercontent.com/render/math?math=3%5Csigma)  原则我们知道, 如果我们得到一个样本, 并求出样本均值的观察值  ![math](https://render.githubusercontent.com/render/math?math=%5Cbar%20%7B%20%7B%20X%20%7D_%7B%200%20%7D%20%7D) , 那么  ![math](https://render.githubusercontent.com/render/math?math=P%5Cleft%28%20%5Cmu%20-2%5Cfrac%20%7B%20%5Csigma%20%20%7D%7B%20%5Csqrt%20%7B%20n%20%7D%20%20%7D%20%3C%5Cbar%20%7B%20%7B%20X%20%7D_%7B%200%20%7D%20%7D%20%3C%5Cmu%20%2B2%5Cfrac%20%7B%20%5Csigma%20%20%7D%7B%20%5Csqrt%20%7B%20n%20%7D%20%20%7D%20%20%5Cright%29%20%5Capprox%200.95) , 我们再将这个式子变形即可得  ![math](https://render.githubusercontent.com/render/math?math=P%5Cleft%28%20%5Cbar%20%7B%20%7B%20X%20%7D_%7B%200%20%7D%20%7D%20-2%5Cfrac%20%7B%20%5Csigma%20%20%7D%7B%20%5Csqrt%20%7B%20n%20%7D%20%20%7D%20%3C%5Cmu%20%3C%5Cbar%20%7B%20%7B%20X%20%7D_%7B%200%20%7D%20%7D%20%2B2%5Cfrac%20%7B%20%5Csigma%20%20%7D%7B%20%5Csqrt%20%7B%20n%20%7D%20%20%7D%20%20%5Cright%29%20%5Capprox%200.95) , 这个式子的意思就是: 我们要估计的未知参数  ![math](https://render.githubusercontent.com/render/math?math=%5Cmu)  在  ![math](https://render.githubusercontent.com/render/math?math=%5Cleft%28%20%5Cbar%20%7B%20%7B%20X%20%7D_%7B%200%20%7D%20%7D%20-2%5Cfrac%20%7B%20%5Csigma%20%20%7D%7B%20%5Csqrt%20%7B%20n%20%7D%20%20%7D%20%2C%5Cbar%20%7B%20%7B%20X%20%7D_%7B%200%20%7D%20%7D%20%2B2%5Cfrac%20%7B%20%5Csigma%20%20%7D%7B%20%5Csqrt%20%7B%20n%20%7D%20%20%7D%20%20%5Cright%29)  这个区间内的概率约等于95%. 
4. 3 中的结论, 我们可以换一种等价的说法或思考的角度, 也就是说: **如果我们要求未知参数的真值在某个区间内的概率为 95%, 那么这个区间就得是**  ![math](https://render.githubusercontent.com/render/math?math=%5Cleft%28%20%5Cbar%20%7B%20%7B%20X%20%7D_%7B%200%20%7D%20%7D%20-2%5Cfrac%20%7B%20%5Csigma%20%20%7D%7B%20%5Csqrt%20%7B%20n%20%7D%20%20%7D%20%2C%5Cbar%20%7B%20%7B%20X%20%7D_%7B%200%20%7D%20%7D%20%2B2%5Cfrac%20%7B%20%5Csigma%20%20%7D%7B%20%5Csqrt%20%7B%20n%20%7D%20%20%7D%20%20%5Cright%29) . 这个 95% 叫做**置信水平**  ![math](https://render.githubusercontent.com/render/math?math=1-%5Calpha) ,  ![math](https://render.githubusercontent.com/render/math?math=%5Calpha) 为**弃真错误**, 得到的区间成为**置信区间 (Confidence interval) **, 区间的上下限称为**置信上限**和**置信下限**. 
5. 但是  ![math](https://render.githubusercontent.com/render/math?math=3%5Csigma)  原则毕竟有局限性, 我们也不能每次估计时都要求是 95% 的置信水平, 所以为了更精确地估计, 我们需要知道置信水平和置信区间的具体关系. 
6. 我们回到 3 中, 当我们知道  ![math](https://render.githubusercontent.com/render/math?math=%5Cbar%20%7B%20X%20%7D%20%5Csim%20N%5Cleft%28%20%5Cmu%20%2C%5Cfrac%20%7B%20%7B%20%5Csigma%20%20%7D%5E%7B%202%20%7D%20%7D%7B%20n%20%7D%20%20%5Cright%29) ,  ![math](https://render.githubusercontent.com/render/math?math=%5Cbar%7BX%7D)  是一个统计量, 我们可以进一步知道  ![math](https://render.githubusercontent.com/render/math?math=%5Cfrac%20%7B%20%5Cbar%20%7B%20X%20%7D%20-%5Cmu%20%20%7D%7B%20%7B%20%5Csigma%20%20%7D/%7B%20%5Csqrt%20%7B%20n%20%7D%20%20%7D%20%7D%20%5Csim%20N%5Cleft%28%200%2C1%20%5Cright%29) ,  ![math](https://render.githubusercontent.com/render/math?math=%5Cfrac%20%7B%20%5Cbar%20%7B%20X%20%7D%20-%5Cmu%20%20%7D%7B%20%7B%20%5Csigma%20%20%7D/%7B%20%5Csqrt%20%7B%20n%20%7D%20%20%7D%20%7D)  是一个我们构造的统计量  ![math](https://render.githubusercontent.com/render/math?math=z) , 因为其分布是更加简单的单位正态分布, 所以我们用它来分析. 其概率密度图如下: 



![](http://strawberryamoszc.oss-cn-shanghai.aliyuncs.com/2019-06-15-093635.png#align=left&display=inline&height=534&margin=%5Bobject%20Object%5D&originHeight=534&originWidth=650&status=done&style=none&width=650)


7. 那么当我们有了置信水平  ![math](https://render.githubusercontent.com/render/math?math=%5Calpha)  以及  ![math](https://render.githubusercontent.com/render/math?math=z)  的定义, 我们可以得到一个类似的等式:  ![math](https://render.githubusercontent.com/render/math?math=P%5Cleft%28%20-%7B%20z%20%7D_%7B%20%7B%20%5Cfrac%20%7B%20%5Calpha%20%20%7D%7B%202%20%7D%20%20%7D%20%7D%3Cz%3C%7B%20z%20%7D_%7B%20%7B%20%5Cfrac%20%7B%20%5Calpha%20%20%7D%7B%202%20%7D%20%20%7D%20%7D%20%5Cright%29%20%3D1-%5Calpha) , 这个等式就将  ![math](https://render.githubusercontent.com/render/math?math=%5Calpha)  和  ![math](https://render.githubusercontent.com/render/math?math=z)  联系起来, 将  ![math](https://render.githubusercontent.com/render/math?math=z%3D%5Cfrac%20%7B%20%5Cbar%20%7B%20X%20%7D%20-%5Cmu%20%20%7D%7B%20%7B%20%5Csigma%20%20%7D/%7B%20%5Csqrt%20%7B%20n%20%7D%20%20%7D%20%7D)  代入该式, 并做等价变换可得  ![math](https://render.githubusercontent.com/render/math?math=P%5Cleft%28%20%5Cbar%20%7B%20X%20%7D%20-%7B%20z%20%7D_%7B%20%7B%20%5Cfrac%20%7B%20%5Calpha%20%20%7D%7B%202%20%7D%20%20%7D%20%7D%5Cfrac%20%7B%20%5Csigma%20%20%7D%7B%20%5Csqrt%20%7B%20n%20%7D%20%20%7D%20%3C%5Cmu%20%3C%5Cbar%20%7B%20X%20%7D%20%2B%7B%20z%20%7D_%7B%20%7B%20%5Cfrac%20%7B%20%5Calpha%20%20%7D%7B%202%20%7D%20%20%7D%20%7D%5Cfrac%20%7B%20%5Csigma%20%20%7D%7B%20%5Csqrt%20%7B%20n%20%7D%20%20%7D%20%20%5Cright%29%20%3D1-%5Calpha) , 这样在  ![math](https://render.githubusercontent.com/render/math?math=%5Calpha%2C%5Cbar%20%7BX%7D%2C%5Csigma) , 和  ![math](https://render.githubusercontent.com/render/math?math=n)  都已知的情况下, 用这四个量表示出了未知参数  ![math](https://render.githubusercontent.com/render/math?math=%5Cmu)  的置信区间. 
8. 整理思路, 我们如果知道总体分布为正态分布, 并且知道其标准差  ![math](https://render.githubusercontent.com/render/math?math=%5Csigma)  和样本容量  ![math](https://render.githubusercontent.com/render/math?math=n) , 当我们给出置信区间  ![math](https://render.githubusercontent.com/render/math?math=1-%5Calpha)  情况下, 利用得到的一个样本计算出其样本均值  ![math](https://render.githubusercontent.com/render/math?math=%5Cbar%20%7BX%7D) , 我们通过构造统计量  ![math](https://render.githubusercontent.com/render/math?math=z)  结合其分布性质, 就可以得到未知参数  ![math](https://render.githubusercontent.com/render/math?math=%5Cmu)  的置信区间, 也就是对  ![math](https://render.githubusercontent.com/render/math?math=%5Cmu)  进行了区间估计: 



![](http://strawberryamoszc.oss-cn-shanghai.aliyuncs.com/2019-06-15-093758.png#align=left&display=inline&height=1038&margin=%5Bobject%20Object%5D&originHeight=1038&originWidth=1840&status=done&style=none&width=1840)


9. 以上是我们对特定总体情况的区间估计, 这个特定情况是总体服从正态分布且已知方差, 但是, 实际中可能我们并不知道方差, 或者我们知道均值想估计方差, 亦或是均值和方差都不知道, 甚至总体可能都不服从正态分布, 这个时候我们就不能通过样本均值这个统计量来进行参数估计了, 就需要通过其他一些统计量, 比如  ![math](https://render.githubusercontent.com/render/math?math=%7B%5Cchi%7D%5E2%20%2Ct)  等等. 但我们有[区间估计与假设检验表](http://strawberryamoszc.oss-cn-shanghai.aliyuncs.com/2019-06-15-%E5%8C%BA%E9%97%B4%E4%BC%B0%E8%AE%A1%E4%B8%8E%E5%81%87%E8%AE%BE%E6%A3%80%E9%AA%8C%E5%85%AC%E5%BC%8F%E8%A1%A8.doc), 通过这个表我们可以快速判断自己应该使用哪个统计量以及估计或统计方法, 这是十分方便的. 
10. 样本容量越大, 置信区间越窄; 置信度越高, 置信区间越宽. 
