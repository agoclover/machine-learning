<a name="index">**Contents**</a>

<a href="#0">方差分析</a>  
&emsp;<a href="#1">单因素试验的方差分析</a>  
&emsp;&emsp;<a href="#2">背景</a>  
&emsp;&emsp;<a href="#3">为什么是方差分析? </a>  
&emsp;&emsp;&emsp;<a href="#4">为什么不直接比较均值? </a>  
&emsp;&emsp;&emsp;<a href="#5">为什么不用 t 检验? </a>  
&emsp;&emsp;<a href="#6">前提假设</a>  
&emsp;&emsp;<a href="#7">原假设</a>  
&emsp;&emsp;<a href="#8">平方和的分解</a>  
&emsp;&emsp;<a href="#9">自由度</a>  
&emsp;&emsp;<a href="#10">分布与期望</a>  
&emsp;&emsp;<a href="#11">拒绝域</a>  
&emsp;<a href="#12">双因素试验的方差分析</a>  
&emsp;&emsp;<a href="#13">双因素等重复试验的方差分析—有相互作用</a>  
&emsp;&emsp;&emsp;<a href="#14">前提</a>  
&emsp;&emsp;&emsp;<a href="#15">参数与记号</a>  
&emsp;&emsp;&emsp;<a href="#16">假设</a>  
&emsp;&emsp;&emsp;<a href="#17">双因素试验的方差分析表</a>  
&emsp;&emsp;&emsp;<a href="#18">拒绝域</a>  
&emsp;&emsp;<a href="#19">双因素无重复试验的方差分析—无相互作用</a>  
&emsp;&emsp;&emsp;<a href="#20">前提</a>  
&emsp;&emsp;&emsp;<a href="#21">参数与记号</a>  
&emsp;&emsp;&emsp;<a href="#22">假设</a>  
&emsp;&emsp;&emsp;<a href="#23">双因素试验的方差分析表</a>  
&emsp;&emsp;&emsp;<a href="#24">拒绝域</a>  
# <a name="0">方差分析</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

## <a name="1">单因素试验的方差分析</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


### <a name="2">背景</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


首先来说说我们为什么要用单因素方差分析 (one-way ANOVA). 在做一些实验时, 我们通常会把样本分成不同的组, 给予不同的对待. 例如, 我们想研究某种药物在不同剂量下对人们的作用. 我们可能会将病人随机分为同等大小的三组, A 组每天吃一片, B 组每天吃两片, C 组每天吃三片. 因为我们只研究这个药品计量对病人的影响, 所以是单因素分析, 如果想要加入别的因素, 例如, 年龄, 就需要用到多因素分析了. 在上述实验中, 我们给了三种不同的计量, 所以这个药物计量因素下有三个水平 (level) . 实验结束以后, 你老板问你, 这三组病人的表现有显著的区别吗? 这个时候, 你就可以使用 ANOVA 来回答你老板的问题啦. 


虽然 ANOVA 叫做方差分析, 但是他的目的是**检验每个组的平均数是否相同** (敲黑板! ) . 也就是说, ANOVA 的零假设 (null hypothesis) 是  ![math](https://render.githubusercontent.com/render/math?math=H_0%3A%5Cmu_A%3D%5Cmu_B%3D%5Cmu_C) . 现在, 我们换一个角度考虑这个问题, 如果这三组病人的表现并没有显著的区别, 那他们其实是同一个总体的三次随机抽样. 反过来说, 我们想要分析, 是不是有一组病人他们的表现非常与众不同, 让这组病人不是来自同一个总体. 


### <a name="3">为什么是方差分析? </a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


#### <a name="4">为什么不直接比较均值? </a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


举个例子,  ![math](https://render.githubusercontent.com/render/math?math=%7BA%7D_%7B1%7D)  组: 29, 30, 31； ![math](https://render.githubusercontent.com/render/math?math=%7BA%7D_%7B2%7D) 组: 3, 31, 41.  ![math](https://render.githubusercontent.com/render/math?math=%7BA%7D_%7B1%7D)  组均值为30,  ![math](https://render.githubusercontent.com/render/math?math=%7BA%7D_%7B2%7D)  组均值 25, 看起来  ![math](https://render.githubusercontent.com/render/math?math=%7BA%7D_%7B1%7D)  组大一些, 但实际上  ![math](https://render.githubusercontent.com/render/math?math=%7BA%7D_%7B2%7D)  组有两个值都大于  ![math](https://render.githubusercontent.com/render/math?math=%7BA%7D_%7B2%7D)  组. 


这是因为, 不同组极端值可能会影响到均值, 从而给判断造成误导. 


#### <a name="5">为什么不用 t 检验? </a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


我们有一个样本后进行一次 t 检验, 在这里, 每一组就相当于一个样本, 那么比如有三组,   ![math](https://render.githubusercontent.com/render/math?math=%7B%20C%20%7D_%7B%203%20%7D%5E%7B%201%20%7D)  就要做 3 次独立的  ![math](https://render.githubusercontent.com/render/math?math=t)  检验. 但是  ![math](https://render.githubusercontent.com/render/math?math=t)  检验是每次给定一个显著性水平, 比如我们给定  ![math](https://render.githubusercontent.com/render/math?math=%5Calpha%3D0.05) , 也就是每次犯错的概率为 0.05, 那么每次不犯错的概率是 0.95, 三次不犯错的概率为  ![math](https://render.githubusercontent.com/render/math?math=0.95%5E3%3D0.857375) , 那么我们犯错的概率就高达 0.142625. 


而方差分析是一次检验, 犯错的概率就小很多, 但方差分析也有局限性, 它只能检验各组之间的均值是否有差异, 并不能给出谁大谁小, 所以, 适当时候有必要方差分析后, 再进行  ![math](https://render.githubusercontent.com/render/math?math=t)  检验. 


### <a name="6">前提假设</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


在具体说如何理解 ANOVA 之前, 我们先来说 ANOVA 有哪些假设. 如果你的实验不能满足 ANOVA 的假设, 那你需要考虑别的分析方法或者改变实验设计. ANOVA 有主要有以下 3 个假设: 


1. **方差的同质性 (homogeneity of variance) **. 可以理解为每组样本背后的总体 (也叫族群) 都有相同的方差；
2. **族群遵循正态分布**；
3. **每一次抽样都是独立的**. 在我们的例子中, 每一个病人只能提供一个数据. 对于一些实验一个样本需要提供多个数据, 有其他相应的 ANOVA 分析方法. 



### <a name="7">原假设</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


 ![math](https://render.githubusercontent.com/render/math?math=%7B%20H%20%7D_%7B%200%20%7D%3A%7B%20%5Cmu%20%20%7D_%7B%201%20%7D%3D%7B%20%5Cmu%20%20%7D_%7B%202%20%7D%3D...%3D%7B%20%5Cmu%20%20%7D_%7B%20s%20%7D) 


 ![math](https://render.githubusercontent.com/render/math?math=%7B%20H%20%7D_%7B%201%20%7D%3A%7B%20%5Cmu%20%20%7D_%7B%201%20%7D%2C%7B%20%5Cmu%20%20%7D_%7B%202%20%7D%2C...%2C%7B%20%5Cmu%20%20%7D_%7B%20s%20%7D)  不全相等


### <a name="8">平方和的分解</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


假设我们得到的抽样结果是这样的: 


![](http://strawberryamoszc.oss-cn-shanghai.aliyuncs.com/2019-09-01-123224.jpg#align=left&display=inline&height=418&margin=%5Bobject%20Object%5D&originHeight=418&originWidth=720&status=done&style=none&width=720)


![](http://strawberryamoszc.oss-cn-shanghai.aliyuncs.com/2019-09-01-123225.jpg#align=left&display=inline&height=235&margin=%5Bobject%20Object%5D&originHeight=235&originWidth=720&status=done&style=none&width=720)


现在, 我们终于可以来看方差分析. 首先我们来看**单因素试验方差分析表**: 

| 方差来源 | 平方和 | 自由度 | 均方 | F比 |
| --- | --- | --- | --- | --- |
| 因素 A |  ![math](https://render.githubusercontent.com/render/math?math=%7BS%7D_%7BA%7D)  | s-1 |  ![math](https://render.githubusercontent.com/render/math?math=%7B%20%5Cbar%20%7B%20S%20%7D%20%20%7D_%7B%20A%20%7D%3D%5Cfrac%20%7B%20%7B%20S%20%7D_%7B%20A%20%7D%20%7D%7B%20s-1%20%7D)  |  ![math](https://render.githubusercontent.com/render/math?math=F%3D%5Cfrac%20%7B%20%7B%20%5Cbar%20%7B%20S%20%7D%20%20%7D_%7B%20A%20%7D%20%7D%7B%20%7B%20%5Cbar%20%7B%20S%20%7D%20%20%7D_%7B%20E%20%7D%20%7D)  |
| 误差 |  ![math](https://render.githubusercontent.com/render/math?math=%7BS%7D_%7BE%7D)  | n-s |  ![math](https://render.githubusercontent.com/render/math?math=%7B%20%5Cbar%20%7B%20S%20%7D%20%20%7D_%7B%20E%20%7D%3D%5Cfrac%20%7B%20%7B%20S%20%7D_%7B%20E%20%7D%20%7D%7B%20n-s%20%7D)  |  |
| 总和 |  ![math](https://render.githubusercontent.com/render/math?math=%7BA%7D_%7BT%7D)  | n-1(即总样本方差自由度) |  |  |



**总偏差平方和**:



![math](https://render.githubusercontent.com/render/math?math=%7B%20S%20%7D_%7B%20T%20%7D%3D%5Csum%20_%7B%20j%3D1%20%7D%5E%7B%20s%20%7D%7B%20%5Csum%20_%7B%20i%3D1%20%7D%5E%7B%20%7B%20n%20%7D_%7B%20j%20%7D%20%7D%7B%20%7B%20%5Cleft%28%20%7B%20%7B%20X%20%7D_%7B%20ij%20%7D%20%7D-%5Cbar%20%7B%20X%20%7D%20%20%5Cright%29%20%20%7D%5E%7B%202%20%7D%20%7D%20%20%7D)



我们可以将其分解: 



![math](https://render.githubusercontent.com/render/math?math=%5Cbegin%7Bequation%7D%0A%5Cbegin%7Baligned%7D%0A%7B%20S%20%7D_%7B%20T%20%7D%0A%20%20%20%26%3D%5Csum%20_%7B%20j%3D1%20%7D%5E%7B%20s%20%7D%7B%20%5Csum%20_%7B%20i%3D1%20%7D%5E%7B%20%7B%20n%20%7D_%7B%20j%20%7D%20%7D%7B%20%7B%20%5Cleft%28%20%7B%20%7B%20X%20%7D_%7B%20ij%20%7D%20%7D-%5Cbar%20%7B%20X%20%7D%20%20%5Cright%29%20%20%7D%5E%7B%202%20%7D%20%7D%20%20%7D%20%0A%5C%5C%20%26%3D%5Csum%20_%7B%20j%3D1%20%7D%5E%7B%20s%20%7D%7B%20%5Csum%20_%7B%20i%3D1%20%7D%5E%7B%20%7B%20n%20%7D_%7B%20j%20%7D%20%7D%7B%20%7B%20%5Cleft%5B%20%5Cleft%28%20%7B%20%7B%20X%20%7D_%7B%20ij%20%7D%20%7D-%7B%20%5Cbar%20%7B%20X%20%7D%20%20%7D_%7B%20%5Cbullet%20j%20%7D%20%5Cright%29%20%2B%5Cleft%28%20%7B%20%5Cbar%20%7B%20X%20%7D%20%20%7D_%7B%20%5Cbullet%20j%20%7D-%5Cbar%20%7B%20X%20%7D%20%20%5Cright%29%20%20%5Cright%5D%20%20%7D%5E%7B%202%20%7D%20%7D%20%20%7D%20%0A%5C%5C%20%26%3D%5Csum%20_%7B%20j%3D1%20%7D%5E%7B%20s%20%7D%7B%20%5Csum%20_%7B%20i%3D1%20%7D%5E%7B%20%7B%20n%20%7D_%7B%20j%20%7D%20%7D%7B%20%7B%20%5Cleft%28%20%7B%20%7B%20X%20%7D_%7B%20ij%20%7D%20%7D-%7B%20%5Cbar%20%7B%20X%20%7D%20%20%7D_%7B%20%5Cbullet%20j%20%7D%20%5Cright%29%20%20%7D%5E%7B%202%20%7D%20%7D%20%20%7D%20%2B%5Csum%20_%7B%20j%3D1%20%7D%5E%7B%20s%20%7D%7B%20%5Csum%20_%7B%20i%3D1%20%7D%5E%7B%20%7B%20n%20%7D_%7B%20j%20%7D%20%7D%7B%20%7B%20%5Cleft%28%20%7B%20%5Cbar%20%7B%20X%20%7D%20%20%7D_%7B%20%5Cbullet%20j%20%7D-%5Cbar%20%7B%20X%20%7D%20%20%5Cright%29%20%20%7D%5E%7B%202%20%7D%20%7D%20%20%7D%20%0A%5C%5C%20%26%3D%7B%20S%20%7D_%7B%20E%20%7D%2B%7B%20S%20%7D_%7B%20A%20%7D%0A%5Cend%7Baligned%7D%0A%5Cend%7Bequation%7D)




 ![math](https://render.githubusercontent.com/render/math?math=%7BS%7D_%7BE%7D) : 误差平方和


 ![math](https://render.githubusercontent.com/render/math?math=%7BS%7D_%7BA%7D) : 效应平方和


### <a name="9">自由度</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


 ![math](https://render.githubusercontent.com/render/math?math=%7BS%7D_%7BE%7D) : **比较简单的理解方法是, 每组 (即每个  ![math](https://render.githubusercontent.com/render/math?math=j)  ) 是  ![math](https://render.githubusercontent.com/render/math?math=%7B%20n%20%7D_%7B%20j%20%7D-1%2Cs)  个组一共 **n-s；


 ![math](https://render.githubusercontent.com/render/math?math=%7BS%7D_%7BA%7D) : **比较简单的理解方法是, 将每组数据的均值看成一个数据**, 共  ![math](https://render.githubusercontent.com/render/math?math=s)  个, 求这  ![math](https://render.githubusercontent.com/render/math?math=s)  个数据的方差, 方差自由度为 **s-1**  (实际需要严谨的证明) ；


### <a name="10">分布与期望</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


 ![math](https://render.githubusercontent.com/render/math?math=%7BS%7D_%7BE%7D) 


由于  ![math](https://render.githubusercontent.com/render/math?math=%5Cfrac%20%7B%20%5Csum%20_%7B%20i%3D1%20%7D%5E%7B%20%7B%20n%20%7D_%7B%201%20%7D%20%7D%7B%20%7B%20%5Cleft%28%20%7B%20X%20%7D_%7B%20ij%20%7D-%7B%20%5Cbar%20%7B%20X%20%7D%20%20%7D_%7B%20%5Cbullet%20j%20%7D%20%5Cright%29%20%20%7D%5E%7B%202%20%7D%20%7D%20%20%7D%7B%20%7B%20%5Csigma%20%20%7D%5E%7B%202%20%7D%20%7D%20%5Csim%20%7B%20%5Cchi%20%20%7D%5E%7B%202%20%7D%5Cleft%28%20%7B%20n%20%7D_%7B%20j%20%7D-1%20%5Cright%29) , 且各  ![math](https://render.githubusercontent.com/render/math?math=X_%7Bij%7D)  相互独立, 由卡方分布可加性知  ![math](https://render.githubusercontent.com/render/math?math=%5Cfrac%20%7B%20%7B%20S%20%7D_%7B%20E%20%7D%20%7D%7B%20%7B%20%5Csigma%20%20%7D%5E%7B%202%20%7D%20%7D%20%5Csim%20%7B%20%5Cchi%20%20%7D%5E%7B%202%20%7D%5Cleft%28%20%7B%20n%20%7D-s%20%5Cright%29)  , 这也再次说明误差平方和的自由度为 **n-s** . 


故  ![math](https://render.githubusercontent.com/render/math?math=E%5Cleft%28%20%7B%20S%20%7D_%7B%20E%20%7D%20%5Cright%29%20%3D%5Cleft%28%20n-s%20%5Cright%29%20%7B%20%5Csigma%20%20%7D%5E%7B%202%20%7D) 


 ![math](https://render.githubusercontent.com/render/math?math=%7BS%7D_%7BA%7D) 


可以推出 (过程略)  ![math](https://render.githubusercontent.com/render/math?math=E%5Cleft%28%20%7B%20S%20%7D_%7B%20A%20%7D%20%5Cright%29%20%3D%5Cleft%28%20s-1%20%5Cright%29%20%7B%20%5Csigma%20%20%7D%5E%7B%202%20%7D%2B%5Csum%20_%7B%20j%3D1%20%7D%5E%7B%20s%20%7D%7B%20%7B%20n%20%7D_%7B%20j%20%7D%7B%20%5Cdelta%20%20%7D_%7B%20j%20%7D%5E%7B%202%20%7D%20%7D) , 其中  ![math](https://render.githubusercontent.com/render/math?math=%5Cdelta_j%3D%5Cmu_j-%5Cmu) . 


进一步还有: 


1.  ![math](https://render.githubusercontent.com/render/math?math=%7BS%7D_%7BA%7D)  与  ![math](https://render.githubusercontent.com/render/math?math=%7BS%7D_%7BE%7D)  独立；
2. 当  ![math](https://render.githubusercontent.com/render/math?math=%7BH%7D_%7B0%7D)  为真时,  ![math](https://render.githubusercontent.com/render/math?math=%5Cfrac%20%7B%20%7B%20S%20%7D_%7B%20A%20%7D%20%7D%7B%20%7B%20%5Csigma%20%20%7D%5E%7B%202%20%7D%20%7D%20%5Csim%20%7B%20%5Cchi%20%20%7D%5E%7B%202%20%7D%5Cleft%28%20s-1%20%5Cright%29)  . 



### <a name="11">拒绝域</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


从上一小节分布和期望, 我们可以总结以下几点: 


1.  ![math](https://render.githubusercontent.com/render/math?math=%7BS%7D_%7BA%7D)  与  ![math](https://render.githubusercontent.com/render/math?math=%7BS%7D_%7BE%7D)  独立；
2.  ![math](https://render.githubusercontent.com/render/math?math=%5Cfrac%20%7B%20%7B%20S%20%7D_%7B%20E%20%7D%20%7D%7B%20%7B%20%5Csigma%20%20%7D%5E%7B%202%20%7D%20%7D%20%5Csim%20%7B%20%5Cchi%20%20%7D%5E%7B%202%20%7D%5Cleft%28%20%7B%20n%20%7D-s%20%5Cright%29) , 因此无论  ![math](https://render.githubusercontent.com/render/math?math=H_0)  是否为真,   ![math](https://render.githubusercontent.com/render/math?math=E%5Cleft%28%20%7B%20S%20%7D_%7B%20E%20%7D%20%5Cright%29%20%3D%5Cleft%28%20n-s%20%5Cright%29%20%7B%20%5Csigma%20%20%7D%5E%7B%202%20%7D) ；
3. 只有当  ![math](https://render.githubusercontent.com/render/math?math=H_0)  为真时,  ![math](https://render.githubusercontent.com/render/math?math=%5Cfrac%20%7B%20%7B%20S%20%7D_%7B%20A%20%7D%20%7D%7B%20%7B%20%5Csigma%20%20%7D%5E%7B%202%20%7D%20%7D%20%5Csim%20%7B%20%5Cchi%20%20%7D%5E%7B%202%20%7D%5Cleft%28%20s-1%20%5Cright%29)  ,  ![math](https://render.githubusercontent.com/render/math?math=E%5Cleft%28%20%7B%20S%20%7D_%7B%20A%20%7D%20%5Cright%29%20%3D%5Cleft%28%20s-1%20%5Cright%29%20%7B%20%5Csigma%20%20%7D%5E%7B%202%20%7D) ；而当  ![math](https://render.githubusercontent.com/render/math?math=H_1)  为真时,  ![math](https://render.githubusercontent.com/render/math?math=E%5Cleft%28%20%7B%20S%20%7D_%7B%20A%20%7D%20%5Cright%29%20%3D%5Cleft%28%20s-1%20%5Cright%29%20%7B%20%5Csigma%20%20%7D%5E%7B%202%20%7D%2B%5Csum%20_%7B%20j%3D1%20%7D%5E%7B%20s%20%7D%7B%20%7B%20n%20%7D_%7B%20j%20%7D%7B%20%5Cdelta%20%20%7D_%7B%20j%20%7D%5E%7B%202%20%7D%20%7D%20%3E%5Cleft%28%20s-1%20%5Cright%29%20%7B%20%5Csigma%20%20%7D%5E%7B%202%20%7D) ；



而两个独立方差一般用F检验, 所以我们考虑**统计量**: 




![math](https://render.githubusercontent.com/render/math?math=F%3D%5Cfrac%20%7B%20%7B%20%7B%20S%20%7D_%7B%20A%20%7D%20%7D/%7B%20%5Cleft%28%20s-1%20%5Cright%29%20%20%7D%20%7D%7B%20%7B%20%7B%20S%20%7D_%7B%20E%20%7D%20%7D/%7B%20%5Cleft%28%20n-s%20%5Cright%29%20%20%7D%20%7D%20%3D%7B%20%5Cfrac%20%7B%20%7B%20%7B%20S%20%7D_%7B%20A%20%7D%20%7D/%7B%20%7B%20%5Csigma%20%20%7D%5E%7B%202%20%7D%20%7D%20%7D%7B%20s-1%20%7D%20%20%7D/%7B%20%5Cfrac%20%7B%20%7B%20%7B%20%7B%20S%20%7D_%7B%20E%20%7D%20%7D/%7B%20%7B%20%5Csigma%20%20%7D%5E%7B%202%20%7D%20%7D%20%7D%20%7D%7B%20n-s%20%7D%20%20%7D)




也就是说, 当  ![math](https://render.githubusercontent.com/render/math?math=%7BH%7D_%7B0%7D)  不真  ![math](https://render.githubusercontent.com/render/math?math=%7BH%7D_%7B1%7D)  为真时, 分子的取值有偏大的趋势, 于是**拒绝域形式**: 




![math](https://render.githubusercontent.com/render/math?math=F%3D%5Cfrac%20%7B%20%7B%20%7B%20S%20%7D_%7B%20A%20%7D%20%7D/%7B%20%5Cleft%28%20s-1%20%5Cright%29%20%20%7D%20%7D%7B%20%7B%20%7B%20S%20%7D_%7B%20E%20%7D%20%7D/%7B%20%5Cleft%28%20n-s%20%5Cright%29%20%20%7D%20%7D%20%5Cge%20k)




而由  ![math](https://render.githubusercontent.com/render/math?math=%7BS%7D_%7BA%7D)  与  ![math](https://render.githubusercontent.com/render/math?math=%7BS%7D_%7BE%7D)  独立, 当  ![math](https://render.githubusercontent.com/render/math?math=%7BH%7D_%7B0%7D)  为真时, 统计量所满足的分布:




![math](https://render.githubusercontent.com/render/math?math=F%5Csim%20F%5Cleft%28%20s-1%2Cn-s%20%5Cright%29)




于是, 我们加上弃真概率  ![math](https://render.githubusercontent.com/render/math?math=%5Calpha) , 可以得到**拒绝域**: 




![math](https://render.githubusercontent.com/render/math?math=F%3D%5Cfrac%20%7B%20%7B%20%7B%20S%20%7D_%7B%20A%20%7D%20%7D/%7B%20%5Cleft%28%20s-1%20%5Cright%29%20%20%7D%20%7D%7B%20%7B%20%7B%20S%20%7D_%7B%20E%20%7D%20%7D/%7B%20%5Cleft%28%20n-s%20%5Cright%29%20%20%7D%20%7D%20%5Cge%20F%5Cleft%28%20s-1%2Cn-s%20%5Cright%29)




其实, 这里的分子和分母就是其他常见解释中的 MSB 和 MSE: 

| 平方和 | 表达式 | 均方 | 方差 | 简称 | 表达式 | 缩写 |
| --- | --- | --- | --- | --- | --- | --- |
|  ![math](https://render.githubusercontent.com/render/math?math=%7BS%7D_%7BA%7D)  |  ![math](https://render.githubusercontent.com/render/math?math=%5Csum%20_%7B%20i%3D1%20%7D%5E%7B%20s%20%7D%7B%20%5Csum%20_%7B%20j%3D1%20%7D%5E%7B%20%7B%20n%20%7D_%7B%20j%20%7D%20%7D%7B%20%7B%20%5Cleft%28%20%7B%20X%20%7D_%7B%20ij%20%7D-%7B%20%5Cbar%20%7B%20X%20%7D%20%20%7D_%7B%20%5Cbullet%20j%20%7D%20%5Cright%29%20%20%7D%5E%7B%202%20%7D%20%7D%20%20%7D)  |  ![math](https://render.githubusercontent.com/render/math?math=%5Cfrac%20%7B%20%7B%20S%20%7D_%7B%20A%20%7D%20%7D%7B%20s-1%20%7D)  | MSB | 组间方差 |  ![math](https://render.githubusercontent.com/render/math?math=%5Cfrac%20%7B%20%5Csum%20_%7B%20i%3D1%20%7D%5E%7B%20s%20%7D%7B%20%5Csum%20_%7B%20j%3D1%20%7D%5E%7B%20%7B%20n%20%7D_%7B%20j%20%7D%20%7D%7B%20%7B%20%5Cleft%28%20%7B%20X%20%7D_%7B%20ij%20%7D-%7B%20%5Cbar%20%7B%20X%20%7D%20%20%7D_%7B%20%5Cbullet%20j%20%7D%20%5Cright%29%20%20%7D%5E%7B%202%20%7D%20%7D%20%20%7D%20%20%7D%7B%20n-s%20%7D)  | Mean Square Between |
|  ![math](https://render.githubusercontent.com/render/math?math=%7BS%7D_%7BE%7D)  |  ![math](https://render.githubusercontent.com/render/math?math=%5Csum%20_%7B%20i%3D1%20%7D%5E%7B%20s%20%7D%7B%20%5Csum%20_%7B%20j%3D1%20%7D%5E%7B%20%7B%20n%20%7D_%7B%20j%20%7D%20%7D%7B%20%7B%20%5Cleft%28%20%7B%20%5Cbar%20%7B%20X%20%7D%20%20%7D_%7B%20%5Cbullet%20j%20%7D-%5Cbar%20%7B%20X%20%7D%20%20%5Cright%29%20%20%7D%5E%7B%202%20%7D%20%7D%20%20%7D)  |  ![math](https://render.githubusercontent.com/render/math?math=%5Cfrac%20%7B%20%7B%20S%20%7D_%7B%20E%20%7D%20%7D%7B%20n-s%20%7D)  | MSE | 组内方差 |  ![math](https://render.githubusercontent.com/render/math?math=%5Cfrac%20%7B%20%5Csum%20_%7B%20i%3D1%20%7D%5E%7B%20s%20%7D%7B%20%5Csum%20_%7B%20j%3D1%20%7D%5E%7B%20%7B%20n%20%7D_%7B%20j%20%7D%20%7D%7B%20%7B%20%5Cleft%28%20%7B%20%5Cbar%20%7B%20X%20%7D%20%20%7D_%7B%20%5Cbullet%20j%20%7D-%5Cbar%20%7B%20X%20%7D%20%20%5Cright%29%20%20%7D%5E%7B%202%20%7D%20%7D%20%20%7D%20%20%7D%7B%20s-1%20%7D)  | Mean Square Error |



## <a name="12">双因素试验的方差分析</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


### <a name="13">双因素等重复试验的方差分析—有相互作用</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


#### <a name="14">前提</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


1.  ![math](https://render.githubusercontent.com/render/math?math=A%2CB)  两因素作用与试验的指标；
2.  ![math](https://render.githubusercontent.com/render/math?math=A)  有  ![math](https://render.githubusercontent.com/render/math?math=r)  个水平；
3.  ![math](https://render.githubusercontent.com/render/math?math=B)  有  ![math](https://render.githubusercontent.com/render/math?math=s)  个水平；
4. 对  ![math](https://render.githubusercontent.com/render/math?math=A%2CB)  的水平的每对组合都做  ![math](https://render.githubusercontent.com/render/math?math=t%28t%E2%89%A52%29) 次试验 (称为等重复试验) . 
5.  ![math](https://render.githubusercontent.com/render/math?math=A%2CB)  之间可能有相互作用. 



#### <a name="15">参数与记号</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


 ![math](https://render.githubusercontent.com/render/math?math=%7B%20X%20%7D_%7B%20ijk%20%7D%5Csim%20N%5Cleft%28%20%7B%20%5Cmu%20%20%7D_%7B%20ij%20%7D%2C%7B%20%5Csigma%20%20%7D%5E%7B%202%20%7D%20%5Cright%29%20%2Ci%3D1%2C2%2C...%2Cr%3Bj%3D1%2C2%2C...%2Cs%3Bk%3D1%2C2%2C...t) 


 ![math](https://render.githubusercontent.com/render/math?math=%5Cmu_%7Bij%7D) ,  ![math](https://render.githubusercontent.com/render/math?math=%5Csigma%5E2)  均为未知参数


总平均  ![math](https://render.githubusercontent.com/render/math?math=%5Cmu%20%3D%5Cfrac%20%7B%201%20%7D%7B%20rs%20%7D%20%5Csum%20_%7B%20i%3D1%20%7D%5E%7B%20r%20%7D%7B%20%5Csum%20_%7B%20j%3D1%20%7D%5E%7B%20s%20%7D%7B%20%7B%20%5Cmu%20%20%7D_%7B%20ij%20%7D%20%7D%20%20%7D) 


 ![math](https://render.githubusercontent.com/render/math?math=%7B%20%5Cmu%20%20%7D_%7B%20i%5Cbullet%20%20%7D%3D%5Cfrac%20%7B%201%20%7D%7B%20s%20%7D%20%5Csum%20_%7B%20j%3D1%20%7D%5E%7B%20s%20%7D%7B%20%7B%20%5Cmu%20%20%7D_%7B%20ij%20%7D%20%7D%20%2Ci%3D1%2C2%2C...r) 


 ![math](https://render.githubusercontent.com/render/math?math=%7B%20%5Cmu%20%20%7D_%7B%20%5Cbullet%20j%20%7D%3D%5Cfrac%20%7B%201%20%7D%7B%20r%20%7D%20%5Csum%20_%7B%20i%3D1%20%7D%5E%7B%20r%20%7D%7B%20%7B%20%5Cmu%20%20%7D_%7B%20ij%20%7D%20%7D%20%2Cj%3D1%2C2%2C...s) 


水平  ![math](https://render.githubusercontent.com/render/math?math=A_i)  的效应  ![math](https://render.githubusercontent.com/render/math?math=%7B%20%5Calpha%20%20%7D_%7B%20i%20%7D%3D%7B%20%5Cmu%20%20%7D_%7B%20i%5Cbullet%20%20%7D-%5Cmu%20%2Ci%3D1%2C2%2C...r) 


水平  ![math](https://render.githubusercontent.com/render/math?math=B_j)  的效应  ![math](https://render.githubusercontent.com/render/math?math=%7B%20%5Cbeta%20%20%7D_%7B%20j%20%7D%3D%7B%20%5Cmu%20%20%7D_%7B%20%5Cbullet%20j%20%7D-%5Cmu%20%2Cj%3D1%2C2%2C...s) 


 ![math](https://render.githubusercontent.com/render/math?math=%7B%20%5Cmu%20%20%7D_%7B%20ij%20%7D%3D%5Cmu%20%2B%7B%20%5Calpha%20%20%7D_%7B%20i%20%7D%2B%7B%20%5Cbeta%20%20%7D_%7B%20j%20%7D%2B%5Cleft%28%20%7B%20%5Cmu%20%20%7D_%7B%20ij%20%7D-%7B%20%5Cmu%20%20%7D_%7B%20i%5Cbullet%20%20%7D-%7B%20%5Cmu%20%20%7D_%7B%20%5Cbullet%20j%20%7D%2B%5Cmu%20%20%5Cright%29%20%3D%5Cmu%20%2B%7B%20%5Calpha%20%20%7D_%7B%20i%20%7D%2B%7B%20%5Cbeta%20%20%7D_%7B%20j%20%7D%2B%7B%20%5Cgamma%20%20%7D_%7B%20ij%20%7D) 


 ![math](https://render.githubusercontent.com/render/math?math=%5Csum%20_%7B%20i%3D1%20%7D%5E%7B%20r%20%7D%7B%20%7B%20a%20%7D_%7B%20i%20%7D%20%7D%20%3D0) 


 ![math](https://render.githubusercontent.com/render/math?math=%5Csum%20_%7B%20j%3D1%20%7D%5E%7B%20s%20%7D%7B%20%7B%20%5Cbeta%20%20%7D_%7B%20j%20%7D%20%7D%20%3D0) 


 ![math](https://render.githubusercontent.com/render/math?math=%5Csum%20_%7B%20i%3D1%20%7D%5E%7B%20r%20%7D%7B%20%7B%20%5Cgamma%20%20%7D_%7B%20ij%20%7D%20%7D%20%3D0%2Cj%3D1%2C2%2C...%2Cs) 


 ![math](https://render.githubusercontent.com/render/math?math=%5Csum%20_%7B%20j%3D1%20%7D%5E%7B%20s%20%7D%7B%20%7B%20%5Cgamma%20%20%7D_%7B%20ij%20%7D%20%7D%20%3D0%2Ci%3D1%2C2%2C...%2Cr) 


**总结**: 


 ![math](https://render.githubusercontent.com/render/math?math=%7B%20X%20%7D_%7B%20ijk%20%7D%3D%5Cmu%20%2B%7B%20%5Calpha%20%20%7D_%7B%20i%20%7D%2B%7B%20%5Cbeta%20%20%7D_%7B%20j%20%7D%2B%7B%20%5Cgamma%20%20%7D_%7B%20ij%20%7D%2B%7B%20%5Cvarepsilon%20%20%7D_%7B%20ijk%20%7D) 


 ![math](https://render.githubusercontent.com/render/math?math=%7B%20%5Cvarepsilon%20%20%7D_%7B%20ijk%20%7D%5Csim%20N%5Cleft%28%200%2C%7B%20%5Csigma%20%20%7D%5E%7B%202%20%7D%20%5Cright%29) , 各  ![math](https://render.githubusercontent.com/render/math?math=%5Cvarepsilon_%7Bij%7D)  独立


 ![math](https://render.githubusercontent.com/render/math?math=i%3D1%2C2%2C...%2Cr%3Bj%3D1%2C2%2C...%2Cs%3Bk%3D1%2C2%2C...t) 


 ![math](https://render.githubusercontent.com/render/math?math=%5Csum%20_%7B%20i%3D1%20%7D%5E%7B%20r%20%7D%7B%20%7B%20a%20%7D_%7B%20i%20%7D%20%7D%20%3D0%2C%5Csum%20_%7B%20j%3D1%20%7D%5E%7B%20s%20%7D%7B%20%7B%20%5Cbeta%20%20%7D_%7B%20j%20%7D%20%7D%20%3D0%2C%5Csum%20_%7B%20i%3D1%20%7D%5E%7B%20r%20%7D%7B%20%7B%20%5Cgamma%20%20%7D_%7B%20ij%20%7D%20%7D%20%3D0%2C%5Csum%20_%7B%20j%3D1%20%7D%5E%7B%20s%20%7D%7B%20%7B%20%5Cgamma%20%20%7D_%7B%20ij%20%7D%20%7D%20%3D0) 


#### <a name="16">假设</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


 ![math](https://render.githubusercontent.com/render/math?math=%7B%20H%20%7D_%7B%2001%20%7D%3A%7B%20%5Calpha%20%20%7D_%7B%201%20%7D%3D%7B%20%5Calpha%20%20%7D_%7B%202%20%7D%3D...%3D%7B%20%5Calpha%20%20%7D_%7B%20r%20%7D%3D0%2C%20%7B%20H%20%7D_%7B%2011%20%7D%3A%7B%20%5Calpha%20%20%7D_%7B%201%20%7D%2C%7B%20%5Calpha%20%20%7D_%7B%202%20%7D%2C...%7B%20%5Calpha%20%20%7D_%7B%20r%20%7D)  不全为 0.


 ![math](https://render.githubusercontent.com/render/math?math=%7B%20H%20%7D_%7B%2002%20%7D%3A%7B%20%5Cbeta%20%20%7D_%7B%201%20%7D%3D%7B%20%5Cbeta%20%20%7D_%7B%202%20%7D%3D...%3D%7B%20%5Cbeta%20%20%7D_%7B%20s%20%7D%3D0%2C%20%7B%20H%20%7D_%7B%2012%20%7D%3A%5Cbeta%20_%7B%201%20%7D%2C%7B%20%5Cbeta%20%20%7D_%7B%202%20%7D%2C...%7B%20%5Cbeta%20%20%7D_%7B%20s%20%7D)  不全为 0.


 ![math](https://render.githubusercontent.com/render/math?math=%7B%20H%20%7D_%7B%2003%20%7D%3A%7B%20%5Cgamma%20%20%7D_%7B%2011%20%7D%3D%7B%20%5Cgamma%20%20%7D_%7B%2012%20%7D%3D...%3D%7B%20%5Cgamma%20%20%7D_%7B%20rs%20%7D%3D0%2C%20%7B%20H%20%7D_%7B%2013%20%7D%3A%7B%20%5Cgamma%20%20%7D_%7B%2011%20%7D%2C%7B%20%5Cgamma%20%20%7D_%7B%2012%20%7D%2C...%7B%20%5Cgamma%20%20%7D_%7B%20rs%20%7D)  不全为 0.


#### <a name="17">双因素试验的方差分析表</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


与单因素情况类似, 对这些问题的检验方法也是建立在平方和的分解上的, 思路是一样的, 但由于较复杂, 我们直接给出方差分析表: 

| 方差来源 | 平方和 | 自由度 | 均方 | F比 |
| --- | --- | --- | --- | --- |
| 因素A |  ![math](https://render.githubusercontent.com/render/math?math=%7BS%7D_%7BA%7D)  | r-1 |  ![math](https://render.githubusercontent.com/render/math?math=%7B%20%5Cbar%20%7B%20S%20%7D%20%20%7D_%7B%20A%20%7D%3D%5Cfrac%20%7B%20%7B%20S%20%7D_%7B%20A%20%7D%20%7D%7B%20r-1%20%7D)  |  ![math](https://render.githubusercontent.com/render/math?math=%7B%20F%20%7D_%7B%20A%20%7D%3D%5Cfrac%20%7B%20%7B%20%5Cbar%20%7B%20S%20%7D%20%20%7D_%7B%20A%20%7D%20%7D%7B%20%7B%20%5Cbar%20%7B%20S%20%7D%20%20%7D_%7B%20E%20%7D%20%7D)  |
| 因素B |  ![math](https://render.githubusercontent.com/render/math?math=%7BS%7D_%7BB%7D)  | s-1 |  ![math](https://render.githubusercontent.com/render/math?math=%7B%20%5Cbar%20%7B%20S%20%7D%20%20%7D_%7B%20B%20%7D%3D%5Cfrac%20%7B%20%7B%20S%20%7D_%7B%20B%20%7D%20%7D%7B%20s-1%20%7D)  |  ![math](https://render.githubusercontent.com/render/math?math=%7B%20F%20%7D_%7B%20B%20%7D%3D%5Cfrac%20%7B%20%7B%20%5Cbar%20%7B%20S%20%7D%20%20%7D_%7B%20B%20%7D%20%7D%7B%20%7B%20%5Cbar%20%7B%20S%20%7D%20%20%7D_%7B%20E%20%7D%20%7D)  |
| 交互作用 |  ![math](https://render.githubusercontent.com/render/math?math=S_%7BA%20%5Ctimes%20B%7D)  | (r-1)(s-1) |  ![math](https://render.githubusercontent.com/render/math?math=%7B%20%5Cbar%20%7B%20S%20%7D%7D_%7BA%5Ctimes%20B%20%7D%3D%5Cfrac%20%7B%20%7B%20S%20%7D_%7B%20A%5Ctimes%20B%20%7D%20%7D%7B%20%5Cleft%28%20r-1%20%5Cright%29%20%5Cleft%28%20s-1%20%5Cright%29%20%20%7D)  |  ![math](https://render.githubusercontent.com/render/math?math=%7B%20F%20%7D_%7B%20A%20%5Ctimes%20B%20%7D%3D%5Cfrac%20%7B%20%7B%20%5Cbar%20%7B%20S%20%7D%20%20%7D_%7B%20A%20%5Ctimes%20B%20%7D%20%7D%7B%20%7B%20%5Cbar%20%7B%20S%20%7D%20%20%7D_%7B%20E%20%7D%20%7D)  |
| 误差 |  ![math](https://render.githubusercontent.com/render/math?math=%7BS%7D_%7BE%7D)  | rs(t-1) |  ![math](https://render.githubusercontent.com/render/math?math=%7B%20%5Cbar%20%7B%20S%20%7D%20%20%7D_%7B%20E%20%7D%3D%5Cfrac%20%7B%20%7B%20S%20%7D_%7B%20E%20%7D%20%7D%7B%20rs%5Cleft%28%20t-1%20%5Cright%29%20%20%7D)  |  |
| 总和 |  ![math](https://render.githubusercontent.com/render/math?math=%7BS%7D_%7BT%7D)  | rst-1 |  |  |



#### <a name="18">拒绝域</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


同单因素方差分析类似, 这里只做总结: 


1. 当  ![math](https://render.githubusercontent.com/render/math?math=%7BH%7D_%7B01%7D)  为真时, 可以证明  ![math](https://render.githubusercontent.com/render/math?math=%7B%20F%20%7D_A%20%3D%20%5Cfrac%20%7B%20%7B%20%7B%20S%20%7D_%7B%20A%20%7D%20%7D/%7B%20%5Cleft%28%20r-1%20%5Cright%29%20%20%7D%20%7D%7B%20%7B%20%7B%20S%20%7D_%7B%20E%20%7D%20%7D/%7B%20%5Cleft%28%20rs%5Cleft%28%20t-1%20%5Cright%29%20%20%5Cright%29%20%20%7D%20%7D%20%5Csim%20F%5Cleft%28%20r-1%2Crs%5Cleft%28%20t-1%20%5Cright%29%20%20%5Cright%29) 
取显著性水平为  ![math](https://render.githubusercontent.com/render/math?math=%5Calpha) , 得到假设  ![math](https://render.githubusercontent.com/render/math?math=%7BH%7D_%7B01%7D)  的拒绝域为:  ![math](https://render.githubusercontent.com/render/math?math=%7B%20F%20%7D_%7B%20A%20%7D%3D%5Cfrac%20%7B%20%7B%20%7B%20S%20%7D_%7B%20A%20%7D%20%7D/%7B%20%5Cleft%28%20r-1%20%5Cright%29%20%20%7D%20%7D%7B%20%7B%20%7B%20S%20%7D_%7B%20E%20%7D%20%7D/%7B%20%5Cleft%28%20rs%5Cleft%28%20t-1%20%5Cright%29%20%20%5Cright%29%20%20%7D%20%7D%20%5Cge%20F%5Cleft%28%20r-1%2Crs%5Cleft%28%20t-1%20%5Cright%29%20%20%5Cright%29) 
2. 当  ![math](https://render.githubusercontent.com/render/math?math=%7BH%7D_%7B02%7D)  为真时, 可以证明  ![math](https://render.githubusercontent.com/render/math?math=%7B%20F%20%7D_%7B%20B%20%7D%3D%5Cfrac%20%7B%20%7B%20%7B%20S%20%7D_%7B%20B%20%7D%20%7D/%7B%20%5Cleft%28%20s-1%20%5Cright%29%20%20%7D%20%7D%7B%20%7B%20%7B%20S%20%7D_%7B%20E%20%7D%20%7D/%7B%20%5Cleft%28%20rs%5Cleft%28%20t-1%20%5Cright%29%20%20%5Cright%29%20%20%7D%20%7D%20%5Csim%20F%5Cleft%28%20s-1%2Crs%5Cleft%28%20t-1%20%5Cright%29%20%20%5Cright%29) 
取显著性水平为  ![math](https://render.githubusercontent.com/render/math?math=%5Calpha) , 得到假设  ![math](https://render.githubusercontent.com/render/math?math=%7BH%7D_%7B02%7D) 的 拒绝域为:  ![math](https://render.githubusercontent.com/render/math?math=%7B%20F%20%7D_%7B%20B%20%7D%3D%5Cfrac%20%7B%20%7B%20%7B%20S%20%7D_%7B%20B%20%7D%20%7D/%7B%20%5Cleft%28%20s-1%20%5Cright%29%20%20%7D%20%7D%7B%20%7B%20%7B%20S%20%7D_%7B%20E%20%7D%20%7D/%7B%20%5Cleft%28%20rs%5Cleft%28%20t-1%20%5Cright%29%20%20%5Cright%29%20%20%7D%20%7D%20%5Cge%20F%5Cleft%28%20s-1%2Crs%5Cleft%28%20t-1%20%5Cright%29%20%20%5Cright%29) 
3. 当  ![math](https://render.githubusercontent.com/render/math?math=%7BH%7D_%7B03%7D)  为真时, 可以证明  ![math](https://render.githubusercontent.com/render/math?math=%7B%20F%20%7D_%7B%20A%20%5Ctimes%20B%20%7D%3D%5Cfrac%20%7B%20%7B%20%7B%20S%20%7D_%7B%20A%20%5Ctimes%20B%20%7D%20%7D/%7B%20%5Cleft%28%20%5Cleft%28%20r-1%20%5Cright%29%20%5Cleft%28%20s-1%20%5Cright%29%20%20%5Cright%29%20%20%7D%20%7D%7B%20%7B%20%7B%20S%20%7D_%7B%20E%20%7D%20%7D/%7B%20%5Cleft%28%20rs%5Cleft%28%20t-1%20%5Cright%29%20%20%5Cright%29%20%20%7D%20%7D%20%5Csim%20F%5Cleft%28%20%5Cleft%28%20r-1%20%5Cright%29%20%5Cleft%28%20s-1%20%5Cright%29%20%2Crs%5Cleft%28%20t-1%20%5Cright%29%20%20%5Cright%29) 
取显著性水平为  ![math](https://render.githubusercontent.com/render/math?math=%5Calpha) , 得到假设  ![math](https://render.githubusercontent.com/render/math?math=%7BH%7D_%7B03%7D)  的拒绝域为:  ![math](https://render.githubusercontent.com/render/math?math=%7B%20F%20%7D_%7B%20A%20%5Ctimes%20B%20%7D%3D%5Cfrac%20%7B%20%7B%20%7B%20S%20%7D_%7B%20A%20%5Ctimes%20B%20%7D%20%7D/%7B%20%5Cleft%28%20%5Cleft%28%20r-1%20%5Cright%29%20%5Cleft%28%20s-1%20%5Cright%29%20%20%5Cright%29%20%20%7D%20%7D%7B%20%7B%20%7B%20S%20%7D_%7B%20E%20%7D%20%7D/%7B%20%5Cleft%28%20rs%5Cleft%28%20t-1%20%5Cright%29%20%20%5Cright%29%20%20%7D%20%7D%20%5Cge%20F%5Cleft%28%20%5Cleft%28%20r-1%20%5Cright%29%20%5Cleft%28%20s-1%20%5Cright%29%20%2Crs%5Cleft%28%20t-1%20%5Cright%29%20%20%5Cright%29) 



### <a name="19">双因素无重复试验的方差分析—无相互作用</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


#### <a name="20">前提</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


1. A, B两因素作用与试验的指标；
2. A有r个水平；
3. B有s个水平；
4. 对A, B的水平的每对组合都做 1 次试验. 
5. A, B之间不存在相互作用或很小可以忽略. 



#### <a name="21">参数与记号</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


 ![math](https://render.githubusercontent.com/render/math?math=%7B%20X%20%7D_%7B%20ij%20%7D%3D%5Cmu%20%2B%7B%20%5Calpha%20%20%7D_%7B%20i%20%7D%2B%7B%20%5Cbeta%20%20%7D_%7B%20j%20%7D%2B%7B%20%5Cvarepsilon%20%20%7D_%7B%20ij%20%7D) 


 ![math](https://render.githubusercontent.com/render/math?math=%7B%20%5Cvarepsilon%20%20%7D_%7B%20ijk%20%7D%5Csim%20N%5Cleft%28%200%2C%7B%20%5Csigma%20%20%7D%5E%7B%202%20%7D%20%5Cright%29) , 各  ![math](https://render.githubusercontent.com/render/math?math=%5Cvarepsilon_%7Bijk%7D)  独立


 ![math](https://render.githubusercontent.com/render/math?math=i%3D1%2C2%2C...%2Cr%3Bj%3D1%2C2%2C...%2Cs) 


 ![math](https://render.githubusercontent.com/render/math?math=%5Csum%20_%7B%20i%3D1%20%7D%5E%7B%20r%20%7D%7B%20%7B%20a%20%7D_%7B%20i%20%7D%20%7D%20%3D0%2C%5Csum%20_%7B%20j%3D1%20%7D%5E%7B%20s%20%7D%7B%20%7B%20%5Cbeta%20%20%7D_%7B%20j%20%7D%20%7D%20%3D0) 


#### <a name="22">假设</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


 ![math](https://render.githubusercontent.com/render/math?math=%7B%20H%20%7D_%7B%2001%20%7D%3A%7B%20%5Calpha%20%20%7D_%7B%201%20%7D%3D%7B%20%5Calpha%20%20%7D_%7B%202%20%7D%3D...%3D%7B%20%5Calpha%20%20%7D_%7Br%7D%3D0%2C%20%20%7B%20H%20%7D_%7B%2011%20%7D%3A%7B%20%5Calpha%20%20%7D_%7B%201%20%7D%2C%7B%20%5Calpha%20%20%7D_%7B%202%20%7D%2C...%7B%20%5Calpha%20%20%7D_%7B%20r%20%7D)  不全为 0.


 ![math](https://render.githubusercontent.com/render/math?math=%7B%20H%20%7D_%7B%2002%20%7D%3A%7B%20%5Cbeta%20%20%7D_%7B%201%20%7D%3D%7B%20%5Cbeta%20%20%7D_%7B%202%20%7D%3D...%3D%7B%20%5Cbeta%20%20%7D_%7B%20s%20%7D%3D0%2C%20%7B%20H%20%7D_%7B%2012%20%7D%3A%5Cbeta%20_%7B%201%20%7D%2C%7B%20%5Cbeta%20%20%7D_%7B%202%20%7D%2C...%7B%20%5Cbeta%20%20%7D_%7B%20s%20%7D)  不全为0.


#### <a name="23">双因素试验的方差分析表</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


与单因素情况类似, 对这些问题的检验方法也是建立在平方和的分解上的, 思路是一样的, 但由于较复杂, 我们直接给出方差分析表: 

| 方差来源 | 平方和 | 自由度 | 均方 | F比 |
| --- | --- | --- | --- | --- |
| 因素A |  ![math](https://render.githubusercontent.com/render/math?math=%7BS%7D_%7BA%7D)  | r-1 |  ![math](https://render.githubusercontent.com/render/math?math=%7B%20%5Cbar%20%7B%20S%20%7D%20%20%7D_%7B%20A%20%7D%3D%5Cfrac%20%7B%20%7B%20S%20%7D_%7B%20A%20%7D%20%7D%7B%20r-1%20%7D)  |  ![math](https://render.githubusercontent.com/render/math?math=%7B%20F%20%7D_%7B%20A%20%7D%3D%5Cfrac%20%7B%20%7B%20%5Cbar%20%7B%20S%20%7D%20%20%7D_%7B%20A%20%7D%20%7D%7B%20%7B%20%5Cbar%20%7B%20S%20%7D%20%20%7D_%7B%20E%20%7D%20%7D)  |
| 因素B |  ![math](https://render.githubusercontent.com/render/math?math=%7BS%7D_%7BB%7D)  | s-1 |  ![math](https://render.githubusercontent.com/render/math?math=%7B%20%5Cbar%20%7B%20S%20%7D%20%20%7D_%7B%20B%20%7D%3D%5Cfrac%20%7B%20%7B%20S%20%7D_%7B%20B%20%7D%20%7D%7B%20s-1%20%7D)  |  ![math](https://render.githubusercontent.com/render/math?math=%7B%20F%20%7D_%7B%20B%20%7D%3D%5Cfrac%20%7B%20%7B%20%5Cbar%20%7B%20S%20%7D%20%20%7D_%7B%20B%20%7D%20%7D%7B%20%7B%20%5Cbar%20%7B%20S%20%7D%20%20%7D_%7B%20E%20%7D%20%7D)  |
| 误差 |  ![math](https://render.githubusercontent.com/render/math?math=%7BS%7D_%7BE%7D)  | **(r-1)(s-1)** |  ![math](https://render.githubusercontent.com/render/math?math=%7B%20%5Cbar%20%7B%20S%20%7D%20%20%7D_%7B%20E%20%7D%3D%5Cfrac%20%7B%20%7B%20S%20%7D_%7B%20E%20%7D%20%7D%7B%20%5Cleft%28%20r-1%20%5Cright%29%20%5Cleft%28%20s-1%20%5Cright%29%20%20%7D)  |  |
| 总和 |  ![math](https://render.githubusercontent.com/render/math?math=%7BS%7D_%7BT%7D)  | **rs-1** |  |  |



#### <a name="24">拒绝域</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>


同单因素方差分析类似, 这里只做总结: 


1. 当  ![math](https://render.githubusercontent.com/render/math?math=%7BH%7D_%7B01%7D)  为真时, 可以证明   ![math](https://render.githubusercontent.com/render/math?math=%7B%20F%20%7D_%7B%20A%20%7D%3D%5Cfrac%20%7B%20%7B%20%7B%20S%20%7D_%7B%20A%20%7D%20%7D/%7B%20%5Cleft%28%20r-1%20%5Cright%29%20%20%7D%20%7D%7B%20%7B%20%7B%20S%20%7D_%7B%20E%20%7D%20%7D/%7B%20%5Cleft%28%20%5Cleft%28%20r-1%20%5Cright%29%20%5Cleft%28%20s-1%20%5Cright%29%20%20%5Cright%29%20%20%7D%20%7D%20%5Csim%20F%5Cleft%28%20r-1%2C%5Cleft%28%20r-1%20%5Cright%29%20%5Cleft%28%20s-1%20%5Cright%29%20%20%5Cright%29) 
取显著性水平为  ![math](https://render.githubusercontent.com/render/math?math=%5Calpha) , 得到假设  ![math](https://render.githubusercontent.com/render/math?math=%7BH%7D_%7B01%7D)  的拒绝域为:  ![math](https://render.githubusercontent.com/render/math?math=%7B%20F%20%7D_%7B%20A%20%7D%3D%5Cfrac%20%7B%20%7B%20%7B%20S%20%7D_%7B%20A%20%7D%20%7D/%7B%20%5Cleft%28%20r-1%20%5Cright%29%20%20%7D%20%7D%7B%20%7B%20%7B%20S%20%7D_%7B%20E%20%7D%20%7D/%7B%20%5Cleft%28%20%5Cleft%28%20r-1%20%5Cright%29%20%5Cleft%28%20s-1%20%5Cright%29%20%20%5Cright%29%20%20%7D%20%7D%20%5Cge%20F%5Cleft%28%20r-1%2C%5Cleft%28%20r-1%20%5Cright%29%20%5Cleft%28%20s-1%20%5Cright%29%20%20%5Cright%29) 
2. 当  ![math](https://render.githubusercontent.com/render/math?math=%7BH%7D_%7B02%7D)  为真时, 可以证明  ![math](https://render.githubusercontent.com/render/math?math=%7B%20F%20%7D_%7B%20B%20%7D%3D%5Cfrac%20%7B%20%7B%20%7B%20S%20%7D_%7B%20B%20%7D%20%7D/%7B%20%5Cleft%28%20s-1%20%5Cright%29%20%20%7D%20%7D%7B%20%7B%20%7B%20S%20%7D_%7B%20E%20%7D%20%7D/%7B%20%5Cleft%28%20%5Cleft%28%20r-1%20%5Cright%29%20%5Cleft%28%20s-1%20%5Cright%29%20%20%5Cright%29%20%20%7D%20%7D%20%5Csim%20F%5Cleft%28%20s-1%2C%5Cleft%28%20r-1%20%5Cright%29%20%5Cleft%28%20s-1%20%5Cright%29%20%20%5Cright%29) 
取显著性水平为  ![math](https://render.githubusercontent.com/render/math?math=%5Calpha) , 得到假设  ![math](https://render.githubusercontent.com/render/math?math=%7BH%7D_%7B02%7D)  的拒绝域为:  ![math](https://render.githubusercontent.com/render/math?math=%7B%20F%20%7D_%7B%20B%20%7D%3D%5Cfrac%20%7B%20%7B%20%7B%20S%20%7D_%7B%20B%20%7D%20%7D/%7B%20%5Cleft%28%20s-1%20%5Cright%29%20%20%7D%20%7D%7B%20%7B%20%7B%20S%20%7D_%7B%20E%20%7D%20%7D/%7B%20%5Cleft%28%20%5Cleft%28%20r-1%20%5Cright%29%20%5Cleft%28%20s-1%20%5Cright%29%20%20%5Cright%29%20%20%7D%20%7D%20%5Cge%20F%5Cleft%28%20s-1%2C%5Cleft%28%20r-1%20%5Cright%29%20%5Cleft%28%20s-1%20%5Cright%29%20%20%5Cright%29) 
