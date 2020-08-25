# 假设检验

## 基本思路


## 正太总体-均值


### 单个正太总体-均值


#### 方差已知- Z 检验


#### 方差未知- t 检验


### 两个正太总体-均值差- t 检验


### 基于成对数据的检验- t 检验


## 正太总体-方差


### 单个总体- 卡方检验


### 两个总体- F 检验


## 置信区间与假设检验之间的关系


## 样本容量的选取


## 分布拟合检验


上面介绍的各种检验方法都是在总体分布形式为已知的前提下进行的讨论, 但在实际问题中, 有时不能知道总体服从什么类型的分布, 这时就要根据样本来检验关于分布的假设. 


这里通过  ![math](https://render.githubusercontent.com/render/math?math=%7B%20%5Cchi%20%20%7D%5E%7B%202%20%7D)  拟合检验法, 来检验总体是否具有某一个指定的分布或属于某一个分布族 (即分布中有未知参数) . 


还介绍专用于检验分布是否为正态的偏度和峰度检验法. 


### 卡方拟合检验法


#### 假设前提


**记：** ![math](https://render.githubusercontent.com/render/math?math=F%5Cleft%28%20x%20%5Cright%29)  为总体X的位置的分布函数. 


**假设：**  ![math](https://render.githubusercontent.com/render/math?math=%7B%20F%20%7D_%7B%200%20%7D%5Cleft%28%20x%20%5Cright%29) 是形式已知, 但可能含有若干个未知参数的分布函数. 


**检验假设：**  ![math](https://render.githubusercontent.com/render/math?math=%7B%20H%20%7D_%7B%200%20%7D%3AF%5Cleft%28%20x%20%5Cright%29%20%3D%7B%20F%20%7D_%7B%200%20%7D%5Cleft%28%20x%20%5Cright%29%20%5Cquad%20%5Cforall%20x%5Cin) 


**注意：**


1. 一般比如检验是否符合孟德尔遗传定律这种没有参数的, 但大多是检验有参数的分布, 比如检验是否符合泊松分布, 泊松分布是有参数  ![math](https://render.githubusercontent.com/render/math?math=%5Clambda)  的, 这类有参数的分布拟合假设也叫做分布族的  ![math](https://render.githubusercontent.com/render/math?math=%5Cchi%20%5E2)  拟合检验. 
2. 若总体  ![math](https://render.githubusercontent.com/render/math?math=X)  为离散型, 则原假设  ![math](https://render.githubusercontent.com/render/math?math=%7BH%7D_%7B%200%20%7D) ：总体  ![math](https://render.githubusercontent.com/render/math?math=X)  的分布律为  ![math](https://render.githubusercontent.com/render/math?math=P%5Cleft%5C%7B%20X%3D%7B%20t%20%7D_%7B%20i%20%7D%20%5Cright%5C%7D%20%3D%7B%20p%20%7D_%7B%20i%20%7D%2Ci%3D1%2C2%2C...) 
3. 若总体  ![math](https://render.githubusercontent.com/render/math?math=X)  为连续型, 则原假设  ![math](https://render.githubusercontent.com/render/math?math=%7BH%7D_%7B%200%20%7D) ：总体  ![math](https://render.githubusercontent.com/render/math?math=X)  的概率密度为  ![math](https://render.githubusercontent.com/render/math?math=f%5Cleft%28%20x%20%5Cright%29) 
4. 备择假设是除了这个分布之外所有的分布, 故不用写出. 



#### 拟合优度检验的基本原理和步骤


1. 在  ![math](https://render.githubusercontent.com/render/math?math=%7BH%7D_%7B%200%20%7D)  下, 总体  ![math](https://render.githubusercontent.com/render/math?math=X)  取值的全体分成  ![math](https://render.githubusercontent.com/render/math?math=k)  组, 即  ![math](https://render.githubusercontent.com/render/math?math=k)  个两两不想交的子集  ![math](https://render.githubusercontent.com/render/math?math=%7B%20A%20%7D_%7B%201%20%7D%2C...%2C%7B%20A%20%7D_%7B%20k%20%7D) .
2. 以  ![math](https://render.githubusercontent.com/render/math?math=%7B%20n%20%7D_%7B%20i%20%7D%5Cleft%28%20i%3D1%2C...k%20%5Cright%29)  记样本观察值  ![math](https://render.githubusercontent.com/render/math?math=%7B%20x%20%7D_%7B%201%20%7D%2C...%2C%7B%20x%20%7D_%7B%20n%20%7D)  中落  ![math](https://render.githubusercontent.com/render/math?math=%7B%20A%20%7D_%7B%20i%20%7D)  内的个数 (**实际频数**) , 且 ![math](https://render.githubusercontent.com/render/math?math=%5Csum%20_%7B%20i%3D1%20%7D%5E%7B%20k%20%7D%7B%20%7B%20n%20%7D_%7B%20i%20%7D%20%7D%20%3Dn) .
3. 当  ![math](https://render.githubusercontent.com/render/math?math=%7BH%7D_%7B%200%20%7D)  为真且  ![math](https://render.githubusercontent.com/render/math?math=%7B%20F%20%7D_%7B%200%20%7D%5Cleft%28%20x%20%5Cright%29)  完全已知时, 计算事件  ![math](https://render.githubusercontent.com/render/math?math=%7B%20A%20%7D_%7B%20i%20%7D)  发生的概率  ![math](https://render.githubusercontent.com/render/math?math=%7B%20p%20%7D_%7B%20i%20%7D%3D%7B%20P%20%7D_%7B%20%7B%20F%20%7D_%7B%200%20%7D%20%7D%5Cleft%28%20%7B%20A%20%7D_%7B%20i%20%7D%20%5Cright%29%20%2Ci%3D1%2C...k) ；
当  ![math](https://render.githubusercontent.com/render/math?math=%7B%20F%20%7D_%7B%200%20%7D%5Cleft%28%20x%20%5Cright%29)  含有 ![math](https://render.githubusercontent.com/render/math?math=r)  个未知参数时, 先利用**极大似然法**估计  ![math](https://render.githubusercontent.com/render/math?math=r)  个未知参数, 然后求得  ![math](https://render.githubusercontent.com/render/math?math=%7B%20p%20%7D_%7B%20i%20%7D)  的估计  ![math](https://render.githubusercontent.com/render/math?math=%7B%20%5Chat%20%7B%20p%20%7D%20%20%7D_%7B%20i%20%7D) .
此时称  ![math](https://render.githubusercontent.com/render/math?math=%7B%20n%20%7D%7B%20p%20%7D_%7B%20i%20%7D)  (或  ![math](https://render.githubusercontent.com/render/math?math=%7B%20n%5Chat%20%7B%20p%20%7D%20%20%7D_%7B%20i%20%7D) ) 为**理论频数**.
4. 直观来看, 如果  ![math](https://render.githubusercontent.com/render/math?math=%7BH%7D_%7B%200%20%7D)  成立, 实际频数  ![math](https://render.githubusercontent.com/render/math?math=%7Bn%7D_%7Bi%7D)  与理论频数  ![math](https://render.githubusercontent.com/render/math?math=%7B%20n%20%7D%7B%20p%20%7D_%7B%20i%20%7D)  相差不会太大, 基于这种想法, 我们会选择：

**检验统计量形式**：  ![math](https://render.githubusercontent.com/render/math?math=%5Csum%20_%7B%20i%3D1%20%7D%5E%7B%20k%20%7D%7B%20%7B%20h%20%7D_%7B%20i%20%7D%7B%20%5Cleft%28%20%7B%20n%20%7D_%7B%20i%20%7D-n%7B%20p%20%7D_%7B%20i%20%7D%20%5Cright%29%20%20%7D%5E%7B%202%20%7D%20%7D%20%2C%7B%20h%20%7D_%7B%20i%20%7D%3D%3F) 

**检验的拒绝域形式**：   ![math](https://render.githubusercontent.com/render/math?math=%5Csum%20_%7B%20i%3D1%20%7D%5E%7B%20k%20%7D%7B%20%7B%20h%20%7D_%7B%20i%20%7D%7B%20%5Cleft%28%20%7B%20n%20%7D_%7B%20i%20%7D-n%7B%20p%20%7D_%7B%20i%20%7D%20%5Cright%29%20%20%7D%5E%7B%202%20%7D%20%7D%20%5Cge%20c) 

**统计量分布**：若  ![math](https://render.githubusercontent.com/render/math?math=n)  充分大, 则当  ![math](https://render.githubusercontent.com/render/math?math=%7BH%7D_%7B%200%20%7D)  为真时, 统计量

 ![math](https://render.githubusercontent.com/render/math?math=%7B%20%5Cchi%20%20%7D%5E%7B%202%20%7D%3D%5Csum%20_%7B%20i%3D1%20%7D%5E%7B%20k%20%7D%7B%20%5Cfrac%20%7B%20%7B%20h%20%7D_%7B%20i%20%7D%7B%20%5Cleft%28%20%7B%20n%20%7D_%7B%20i%20%7D-n%7B%20p%20%7D_%7B%20i%20%7D%20%5Cright%29%20%20%7D%5E%7B%202%20%7D%20%7D%7B%20n%7B%20p%20%7D_%7B%20i%20%7D%20%7D%20%20%7D%20%5Coverset%20%7B%20appro%20%7D%7B%20%5Csim%20%20%7D%20%7B%20%5Cchi%20%20%7D%5E%7B%202%20%7D%5Cleft%28%20k-1%20%5Cright%29) 

 ![math](https://render.githubusercontent.com/render/math?math=%7B%20%5Cchi%20%20%7D%5E%7B%202%20%7D%3D%5Csum%20_%7B%20i%3D1%20%7D%5E%7B%20k%20%7D%7B%20%5Cfrac%20%7B%20%7B%20h%20%7D_%7B%20i%20%7D%7B%20%5Cleft%28%20%7B%20n%20%7D_%7B%20i%20%7D-n%7B%20%5Chat%20%7B%20p%20%7D%20%20%7D_%7B%20i%20%7D%20%5Cright%29%20%20%7D%5E%7B%202%20%7D%20%7D%7B%20n%7B%20%5Chat%20%7B%20p%20%7D%20%20%7D_%7B%20i%20%7D%20%7D%20%20%7D%20%5Coverset%20%7B%20appro%20%7D%7B%20%5Csim%20%20%7D%20%7B%20%5Cchi%20%20%7D%5E%7B%202%20%7D%5Cleft%28%20k-r-1%20%5Cright%29) 

其中  ![math](https://render.githubusercontent.com/render/math?math=k)  为分类数,  ![math](https://render.githubusercontent.com/render/math?math=r)  为  ![math](https://render.githubusercontent.com/render/math?math=%7B%20F%20%7D_%7B%200%20%7D%5Cleft%28%20x%20%5Cright%29)  中被估未知参数的个数. 

**检验统计量**:

 ![math](https://render.githubusercontent.com/render/math?math=%7B%20%5Cchi%20%20%7D%5E%7B%202%20%7D%3D%5Csum%20_%7B%20i%3D1%20%7D%5E%7B%20k%20%7D%7B%20%5Cfrac%20%7B%20%7B%20h%20%7D_%7B%20i%20%7D%7B%20%5Cleft%28%20%7B%20n%20%7D_%7B%20i%20%7D-n%7B%20p%20%7D_%7B%20i%20%7D%20%5Cright%29%20%20%7D%5E%7B%202%20%7D%20%7D%7B%20n%7B%20p%20%7D_%7B%20i%20%7D%20%7D%20%20%7D%20%3D%5Csum%20_%7B%20i%3D1%20%7D%5E%7B%20k%20%7D%7B%20%5Cfrac%20%7B%20%7B%20%7B%20n%20%7D_%7B%20i%20%7D%20%7D%5E%7B%202%20%7D%20%7D%7B%20n%7B%20p%20%7D_%7B%20i%20%7D%20%7D%20%20%7D%20-n)   或

 ![math](https://render.githubusercontent.com/render/math?math=%7B%20%5Cchi%20%20%7D%5E%7B%202%20%7D%3D%5Csum%20_%7B%20i%3D1%20%7D%5E%7B%20k%20%7D%7B%20%5Cfrac%20%7B%20%7B%20h%20%7D_%7B%20i%20%7D%7B%20%5Cleft%28%20%7B%20n%20%7D_%7B%20i%20%7D-n%7B%20%5Chat%20%7B%20p%20%7D%20%20%7D_%7B%20i%20%7D%20%5Cright%29%20%20%7D%5E%7B%202%20%7D%20%7D%7B%20n%7B%20%5Chat%20%7B%20p%20%7D%20%20%7D_%7B%20i%20%7D%20%7D%20%20%7D%20%3D%5Csum%20_%7B%20i%3D1%20%7D%5E%7B%20k%20%7D%7B%20%5Cfrac%20%7B%20%7B%20%7B%20n%20%7D_%7B%20i%20%7D%20%7D%5E%7B%202%20%7D%20%7D%7B%20n%7B%20%5Chat%20%7B%20p%20%7D%20%20%7D_%7B%20i%20%7D%20%7D%20%20%7D%20-n) 

**显著水平  ![math](https://render.githubusercontent.com/render/math?math=%5Calpha)  下拒绝域**：

 ![math](https://render.githubusercontent.com/render/math?math=%7B%20%5Cchi%20%20%7D%5E%7B%202%20%7D%3D%5Csum%20_%7B%20i%3D1%20%7D%5E%7B%20k%20%7D%7B%20%5Cfrac%20%7B%20%7B%20%7B%20n%20%7D_%7B%20i%20%7D%20%7D%5E%7B%202%20%7D%20%7D%7B%20n%7B%20p%20%7D_%7B%20i%20%7D%20%7D%20%20%7D%20-n%5Cge%20%7B%20%5Cchi%20%20%7D_%7B%20%5Calpha%20%20%7D%5E%7B%202%20%7D%5Cleft%28%20k-1%20%5Cright%29) ,  (没有参数需要估计) 

 ![math](https://render.githubusercontent.com/render/math?math=%7B%20%5Cchi%20%20%7D%5E%7B%202%20%7D%3D%5Csum%20_%7B%20i%3D1%20%7D%5E%7B%20k%20%7D%7B%20%5Cfrac%20%7B%20%7B%20%7B%20n%20%7D_%7B%20i%20%7D%20%7D%5E%7B%202%20%7D%20%7D%7B%20n%7B%20%5Chat%20%7B%20p%20%7D%20%20%7D_%7B%20i%20%7D%20%7D%20%20%7D%20-n%5Cge%20%7B%20%5Cchi%20%20%7D_%7B%20%5Calpha%20%20%7D%5E%7B%202%20%7D%5Cleft%28%20k-r-1%20%5Cright%29) ,   (有  ![math](https://render.githubusercontent.com/render/math?math=r)  个参数需要估计) 



**卡方拟合检验使用时必须注意：**

 ![math](https://render.githubusercontent.com/render/math?math=n)  要足够大,  ![math](https://render.githubusercontent.com/render/math?math=n%E2%89%A550) ；

 ![math](https://render.githubusercontent.com/render/math?math=n%7B%20p%20%7D_%7B%20i%20%7D)  或  ![math](https://render.githubusercontent.com/render/math?math=n%7B%20%7B%20%5Chat%20%7B%20p%20%7D%20%20%7D_%7B%20i%20%7D%20%7D%5Cge%205) ；

否则应适当合并相邻的类 (组) , 以满足要求. 



### 偏度、峰度检验


## 秩和检验


## 假设检验问题的 P 值法

`p-value` 是指在一个概率模型中, 统计摘要 (如两组样本均值差) 与实际观测数据相同, 或甚至更大这一事件发生的概率. 换言之, 是检验假设零假设成立或表现更严重的可能性. `p-value`若与选定显著性水平 (0.05 或 0.01) 相比更小, 则零假设会被否定而不可接受. 然而这并不直接表明原假设正确. 通常在零假设下, `p-value`是一个服从  ![math](https://render.githubusercontent.com/render/math?math=%5B0%2C1%5D)  区间均匀分布的随机变量, 在实际使用中因样本等各种因素存在不确定性. 产生的结果可能会带来争议. 


简单来说, `p-value`就是**在假设原假设 ( ![math](https://render.githubusercontent.com/render/math?math=%7BH%7D_%7B%200%20%7D) ) 正确时, 出现现状或更差的情况的概率. **


从研究总体中抽取一个随机样本计算检验统计量的值计算概率`p-value`或者说观测的显著水平, 即在假设为真时的前提下, 检验统计量大于或等于实际观测值的概率, 当然要看假设的情况选择单侧`p-value`和双侧`p-value`:


1. 如果`p-value<0.01`, 说明是较强的判定结果, 拒绝假定的参数取值. 
2. 如果`0.01<p-value<0.05`, 说明较弱的判定结果, 拒绝假定的参数取值. 
3. 如果`p-value>0.05`, 说明结果更倾向于接受假定的参数取值. 



可是, 那个年代, 由于硬件的问题, 计算`p-value`并非易事, 人们就采用了统计量检验方法, 也就是我们最初学的  ![math](https://render.githubusercontent.com/render/math?math=t)  值和  ![math](https://render.githubusercontent.com/render/math?math=t)  临界值比较的方法. 统计检验法是在检验之前确定显著性水平  ![math](https://render.githubusercontent.com/render/math?math=%5Calpha) , 也就是说事先确定了拒绝域. 但是, 如果选中相同的  ![math](https://render.githubusercontent.com/render/math?math=%5Calpha) , 所有检验结论的可靠性都一样, 无法给出观测数据与原假设之间不一致程度的精确度量. 只要统计量落在拒绝域, 假设的结果都是一样, 即结果显著. 但实际上, 统计量落在拒绝域不同的地方, 实际上的显著性有较大的差异. 因此, 随着计算机的发展,  ![math](https://render.githubusercontent.com/render/math?math=P)  值的计算不再是个难题, 使得  ![math](https://render.githubusercontent.com/render/math?math=P)  值变成最常用的统计指标之一. 


> 以上关于p-value内容分别摘录自[Wikipedia](https://zh.wikipedia.org/wiki/P%E5%80%BC), [知乎](https://www.zhihu.com/question/23149768/answer/23751377)和[百度百科](https://baike.baidu.com/item/P%E5%80%BC). 

