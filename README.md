# Self-organizing-map-SOM-
自组织神经网络介绍
## 特点
SOM是一种**无监督的**的机器学习方法，同时结合了神经网络算法和聚类算法，可以用于把高维的数据转变为低维数据的同时，将数据按空间距离分类，同时保留他的**拓扑结构**。    
### 竞争层
一般由m*n的方阵组成，在二维空间中，每个节点的相对距离保持不变。同时竞争层的每个神经元有两套不同的坐标，一套是在他的**拓扑空间上的坐标**，例如（0,1）**不会发生变化**，另一套是每个**神经元的权重**（权重的维度与样本属性维度相同），会随着每次迭代而发生改变。     

![image](https://user-images.githubusercontent.com/73262817/127090721-1fa68ee1-1971-4047-8e92-eee26cb501fe.png)

### 算法过程
* step1：确定神经元个数，并根据样本维度赋予神经元微小的随机权重。
* step2：随机选取一个输入样本xi
* step3：遍历所有神经元权重与xi的欧式距离，其中距离最小的为Best Matching Unit，也称为优胜节点
* step4: 在拓扑空间上根据优胜节点选择优胜领域，更新优胜邻域神经元的权重。       
    * 更新权重的主要思路为：优胜节点更新的速度最快，在**拓扑空间中**离优胜节点越近的节点更新越大，越远更新越小。
    * 一般可以采用高斯分布，作为节点距离优胜节点的距离权重。
    * $$
W_{t+1} = W_{t} + \alpha*\theta*(D_{t} - W_{t})
$$


<img src="https://github.com/diobrando-jojo/Self-organizing-map-SOM-/blob/main/som_pic/BMU.png" width="60%" height="60%" />
<img src="https://github.com/diobrando-jojo/Self-organizing-map-SOM-/blob/main/som_pic/diedai.PNG" width="60%" height="60%" />


