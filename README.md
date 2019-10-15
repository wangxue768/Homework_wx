## 文件说明
- handwritten_digits_data.py 与 text_documents.py两个文件是官网上的两个数据集sklearn.datasets.load_di
gits和sklearn.datasets.fetch_20newsgroups的示例。  
- test_handwritten_digits_data.py 与 test_text_documents.py 文件是根据示例进行修改后的文件，每个文件包含7个算法，分别是kmeans，AffinityPropagation，MeanShift，SpectralClustering，AgglomerativeClustering，DBSCAN，GaussianMixture。  

## 运行结果  
### test_handwritten_digits_data.py  
![](https://github.com/wangxue768/Homework_wx/blob/master/kmeans_digits_dataset.png)

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

