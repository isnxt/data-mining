# Clustering
K-means, DBSCAN, Agglomerative Hierarchical Clustering, AffinityPropagation
## 聚类标签：
1. 聚类标签由无意义的整数数字组成，不同的数字代表不同的类别。
2. adjusted_rand_score是通过比较是否将聚类结果与本应该在同一类或不同类的真实类别比较，所以聚类结果和真实标签的数量和名称都可以不同。
## KMeans
算法优点：
1. 原理比较简单，实现也是很容易，收敛速度快。
2. 聚类效果较优。
3. 算法的可解释度比较强。
4. 主要需要调参的参数仅仅是簇数k。
算法缺点：
1. 需要指定类的数目k，且k值的选取不好把握
2. 对于不是凸的数据集比较难收敛
4. 采用迭代方法，得到的结果只是局部最优。
5. 对噪音和异常点比较的敏感。
## DBSCAN
算法优点：
1. 这类算法能克服基于距离的算法只能发现“类圆形”(凸)的聚类的缺点
2. 可发现任意形状的聚类，且对噪声数据不敏感。
3. 不需要指定类的数目
4. 算法中只有两个参数，扫描半径 (eps)和最小包含点数(min_samples)
算法缺点： 
1. 计算复杂度高，不进行任何优化时，算法的时间复杂度是O(N^{2})。
2. 受eps影响较大。在类中的数据分布密度不均匀时，
eps较小时，密度小的cluster会被划分成多个性质相似的cluster；
eps较大时，会使得距离较近且密度较大的cluster被合并成一个cluster。
3. 依赖距离公式的选取，由于维度灾害，距离的度量标准不重要
## Agglomerative Hierarchical Clustering
算法优点：
1. 距离和规则的相似度容易定义，限制少；
3. 不需要指定类的数目
3. 可以发现类的层次关系；
4. 可以聚类成其它形状
算法缺点： 
1. 计算复杂度太高，不进行任何优化时，算法的时间复杂度是O(N^{3})；
3. 算法很可能聚类成链状
## AffinityPropagation
算法优点：
3. 不需要指定类的数目
2. 已有的数据点作为最终的聚类中心，而不是新生成一个族中心。 
3. 模型对数据的初始值不敏感。 
4. 对初始相似度矩阵数据的对称性没有要求。
算法缺点： 
1. 需要事先设置参考度(preference)，而参考度的大小与聚类中心的个数正相关； 
2. 由于AP算法每次迭代都需要更新每个数据点的吸引度值和归属度值，算法复杂度较高。

