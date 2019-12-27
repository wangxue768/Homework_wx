# Data Mining 实验报告
学号：201944768  姓名：王雪
## 项目文件说明
- handwritten_digits_data.py 与 text_documents.py两个文件是官网上的两个数据集sklearn.datasets.load_di
gits和sklearn.datasets.fetch_20newsgroups的示例。  
- test_handwritten_digits_data.py 与 test_text_documents.py 文件是根据示例进行修改后的文件，每个文件包含7个算法，分别是kmeans，AffinityPropagation，MeanShift，SpectralClustering，AgglomerativeClustering，DBSCAN，GaussianMixture。  
## 算法介绍
1.K-Means  
K-Means是典型的聚类算法，K-Means算法中的k表示的是聚类为k个簇，means代表取每一个聚类中数据值的均值作为该簇的中心，或者称为质心，即用每一个的类的质心对该簇进行描述。  

2.Affinity Propagation  
Affinity Propagation聚类算法是基于数据点间的"信息传递"的一种聚类算法。与k-均值算法或k中心点算法不同，AP算法不需要在运行算法之前确定聚类的个数。AP算法寻找的"examplars"即聚类中心点是数据集合中实际存在的点，作为每类的代表。  

3.Mean Shift  
Mean Shift（均值漂移）是基于密度的非参数聚类算法，其算法思想是假设不同簇类的数据集符合不同的概率密度分布，找到任一样本点密度增大的最快方向（最快方向的含义就是Mean Shift），样本密度高的区域对应于该分布的最大值，这些样本点最终会在局部密度最大值收敛，且收敛到相同局部最大值的点被认为是同一簇类的成员。  

4.Spectral Clustering  
Spectral Clustering（谱聚类）是从图论中演化出来的算法，后来在聚类中得到了广泛的应用。它的主要思想是把所有的数据看做空间中的点，这些点之间可以用边连接起来。距离较远的两个点之间的边权重值较低，而距离较近的两个点之间的边权重值较高，通过对所有数据点组成的图进行切图，让切图后不同的子图间边权重和尽可能的低，而子图内的边权重和尽可能的高，从而达到聚类的目的。  

5.Agglomerative Clustering  
Agglomerative Clutsering 是一种自底而上的层次聚类方法，它能够根据指定的相似度或距离定义计算出类之间的距离。  

6.DBSCAN  
DBSCAN(Density-Based Spatial Clustering of Applications with Noise)是一个比较有代表性的基于密度的聚类算法。与划分和层次聚类方法不同，它将簇定义为密度相连的点的最大集合，能够把具有足够高密度的区域划分为簇，并可在噪声的空间数据库中发现任意形状的聚类。  

7.Gaussian Mixture  
Gaussian Mixture（高斯混合模型）是对高斯模型进行简单的扩展，GMM使用多个高斯分布的组合来刻画数据分布。  

## 运行结果  
### test_handwritten_digits_data.py  
![](https://github.com/wangxue768/Homework_wx/blob/master/Homework/kmeans_digits_dataset.png)

n_digits: 10, 	 n_samples 1797, 	 n_features 64  

|init			             |time	 | homo	|compl	|NMI  |labels_true|	label_pred|
----------------------|--------|------|-------|-----|-----------|-----------|
|kmeans   		         |0.41s	  |0.602	|0.650|	0.626 |[0 1 2 ... 8 9 8]|	[0 3 3 ... 3 7 7]|
|AffinityPropagation	|14.44s	|0.932	|0.460	|0.655|[0 1 2 ... 8 9 8]|	[102  86   3 ... 100  34   2]|
|MeanShift		        	|17.93s	|0.014|	0.281	|0.063|[0 1 2 ... 8 9 8]|	[0 0 0 ... 0 0 0]|
|SpectralClustering		|735.62s	|0.001|	0.271	|0.012|[0 1 2 ... 8 9 8]|	[2 2 2 ... 2 2 2]|
|AgglomerativeClustering	|0.49s	|0.758	|0.836	|0.797|[0 1 2 ... 8 9 8]|	[5 1 1 ... 1 1 1]|
|DBSCAN   	          	|0.53s	 | 0.000|	1.000 |0.375 |[0 1 2 ... 8 9 8]|	[-1 -1 -1 ... -1 -1 -1]|
|GaussianMixture		    |0.11s 	|0.000	|1.000 |0.375 | [0 1 2 ... 8 9 8]|[0 0 0 ... 0 0 0]  |

----  
### test_text_documents.py  

|init			             |time	 | homo	|compl	|NMI  |labels_true|	label_pred|
-----------------------|-------|------|-------|-----|-----------|-----------|
|kmeans   		         |3.666s |0.374	|0.567  |0.460|[0 1 1 ... 2 1 1]|[0 3 3 ... 3 3 3]|
|AffinityPropagation	|55.952s	|0.517|0.601	|0.557|[0 1 1 ... 2 1 1]|[0 2 2 ... 1 2 1]|
|MeanShift		        	|2.651s	|0.082|	0.263	|0.147|[0 1 1 ... 2 1 1]|[0 0 0 ... 0 0 0]  | 
|SpectralClustering		|45.504s	|0.002|	0.168	|0.016|[0 1 1 ... 2 1 1]|[3 1 1 ... 0 1 1]|
|AgglomerativeClustering	|2192.298s	|0.000	|1.000|0.000|[0 1 1 ... 2 1 1]|[0 1 1 ... 0 1 1]|
|DBSCAN   	          	|21.226s	 | 0.885|	0.191 |0.411|[0 1 1 ... 2 1 1]|[0 0 0 ... 0 0 0]|
|GaussianMixture		    |90.275s 	|0.000	|1.000 |0.000 |[0 1 1 ... 2 1 1]|[2 1 1 ... 0 1 1]|

## 评价
1. 聚集时间评价
- 数据集handwritten_digits_data  
GaussianMixture< kmeans< AgglomerativeClustering< DBSCAN< AffinityPropagation< MeanShift< SpectralClustering  
- 数据集text_documents  
MeanShift< K-Means< DBSCAN< SpectralClustering< AffinityPropagation< GaussianMixture< AgglomerativeClustering  
2. homogeneity_score  
- 数据集handwritten_digits_data  
GaussianMixture=DBSCAN< SpectralClustering< MeanShift< kmeans< AgglomerativeClustering< AffinityPropagation  
- 数据集text_documents  
AgglomerativeClustering=GaussianMixture< SpectralClustering< MeanShift< K-Means< AffinityPropagation< DBSCAN  
3. completeness score  
- 数据集handwritten_digits_data  
SpectralClustering< MeanShift< AffinityPropagation< kmeans< AgglomerativeClustering< DBSCAN=GaussianMixture  
- 数据集text_documents  
SpectralClustering< DBSCAN< MeanShift<  K-Means< AffinityPropagation< GaussianMixture=AgglomerativeClustering  
4. NMI评价  
- 数据集handwritten_digits_data  
SpectralClustering< MeanShift< DBSCAN= GaussianMixture< kmeans< AffinityPropagation< AgglomerativeClustering  
- 数据集text_documents  
AgglomerativeClustering=GaussianMixture< SpectralClustering< MeanShift< DBSCAN< K-Means< AffinityPropagation  

