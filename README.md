## 文件说明
handwritten_digits_data.py 与 text_documents.py两个文件是官网上的两个数据集示例。  
test_handwritten_digits_data.py 与 test_text_documents.py 文件是根据示例进行修改。  

## 运行结果  
### test_handwritten_digits_data.py  
n_digits: 10, 	 n_samples 1797, 	 n_features 64  

|init			             |time	 | homo	|compl	|NMI  |
----------------------|--------|------|-------|-----|
|kmeans   		         |0.41s	  |0.602	|0.650|	0.626 | 
|AffinityPropagation	|14.44s	|0.932	|0.460	|0.655|  
|MeanShift		        	|17.93s	|0.014|	0.281	|0.063|  
|SpectralClustering		|735.62s	|0.001|	0.271	|0.012|
|AgglomerativeClustering	|0.49s	|0.758	|0.836	|0.797|
|DBSCAN   	          	|0.53s	 | 0.000|	1.000 |0.375 
|GaussianMixture		    |0.11s 	|0.000	|1.000 |0.375 | 

----  
### test_text_documents.py  

|init			             |time	 | homo	|compl	|NMI  |
----------------------|--------|------|-------|-----|
|kmeans   		         |3.666s |0.374	|0.567|	0.460 | 
|AffinityPropagation	|55.952s	|0.517	|0.601	|0.557|  
|MeanShift		        	|2.651s	|0.082|	0.263	|0.147|  
|SpectralClustering		|45.504s	|0.002|	0.168	|0.016|
|AgglomerativeClustering	|2192.298s	|0.000	|1.000|0.000|
|DBSCAN   	          	|21.226s	 | 0.885|	0.191 |0.411 
|GaussianMixture		    |90.275s 	|0.000	|1.000 |0.000 | 


## 评价标准
1. 聚集时间评价
- 数据集handwritten_digits_data  
GaussianMixture< kmeans< AgglomerativeClustering< DBSCAN< AffinityPropagation< MeanShift< SpectralClustering  
- 数据集text_documents  
MeanShift< K-Means< DBSCAN< SpectralClustering< AffinityPropagation< GaussianMixture< AgglomerativeClustering  
2. Homogeneity评价  
- 数据集handwritten_digits_data  
GaussianMixture=DBSCAN< SpectralClustering< MeanShift< kmeans< AgglomerativeClustering< AffinityPropagation  
- 数据集text_documents  
AgglomerativeClustering=GaussianMixture< SpectralClustering< MeanShift< K-Means< AffinityPropagation< DBSCAN  
3. completeness评价  
- 数据集handwritten_digits_data  
SpectralClustering< MeanShift< AffinityPropagation< kmeans< AgglomerativeClustering< DBSCAN=GaussianMixture  
- 数据集text_documents  
SpectralClustering< DBSCAN< MeanShift<  K-Means< AffinityPropagation< GaussianMixture=AgglomerativeClustering  
4. NMI评价  
- 数据集handwritten_digits_data  
SpectralClustering< MeanShift< DBSCAN= GaussianMixture< kmeans< AffinityPropagation< AgglomerativeClustering  
- 数据集text_documents  
AgglomerativeClustering=GaussianMixture< SpectralClustering< MeanShift< DBSCAN< K-Means< AffinityPropagation  

