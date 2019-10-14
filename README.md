# 文件说明
handwritten_digits_data.py 与 text_documents.py两个文件是官网上的两个数据集示例。  
test_handwritten_digits_data.py 与 test_text_documents.py 文件是根据示例进行修改。  

# 运行结果  
## test_handwritten_digits_data.py  
n_digits: 10, 	 n_samples 1797, 	 n_features 64  
_________________________________________________________________
init			             time	  homo	compl	NMI  
kmeans   		         	0.41s	  0.602	0.650	0.626  
AffinityPropagation		14.44s	0.932	0.460	0.655  
MeanShift		        	17.93s	0.014	0.281	0.063  
SpectralClustering		735.62s	0.001	0.271	0.012  
AgglomerativeClustering	0.49s	0.758	0.836	0.797  
DBSCAN   	          	0.53s	  0.000	1.000 0.375  
GaussianMixture		    0.11s 	0.000	1.000 0.375  

----  
## test_text_documents.py  
K-Means done in 3.666s  
Homogeneity: 0.374  
Completeness: 0.567  
NMI: 0.460  

AffinityPropagation done in 55.952s  
Homogeneity: 0.517  
Completeness: 0.601  
NMI: 0.557  

AgglomerativeClustering done in 2192.298s  
Homogeneity: 0.000  
Completeness: 1.000  
NMI: 0.000  

DBSCAN done in 21.226s  
Homogeneity: 0.885  
Completeness: 0.191  
NMI: 0.411  

MeanShift done in 2.651s  
Homogeneity: 0.082  
Completeness: 0.263  
NMI: 0.147  

SpectralClustering done in 45.504s  
Homogeneity: 0.002  
Completeness: 0.168  
NMI: 0.016  

GaussianMixture done in 90.275s  
Homogeneity: 0.000  
Completeness: 1.000  
NMI: 0.000  

# 评价标准
## 聚集时间评价
### 数据集handwritten_digits_data
GaussianMixture< kmeans< AgglomerativeClustering< DBSCAN< AffinityPropagation< MeanShift< SpectralClustering
### 数据集text_documents  
MeanShift< K-Means< DBSCAN< SpectralClustering< AffinityPropagation< GaussianMixture< AgglomerativeClustering
## Homogeneity评价
### 数据集handwritten_digits_data  
GaussianMixture=DBSCAN< SpectralClustering< MeanShift< kmeans< AgglomerativeClustering< AffinityPropagation  
### 数据集text_documents  
AgglomerativeClustering=GaussianMixture< SpectralClustering< MeanShift< K-Means< AffinityPropagation< DBSCAN
## completeness评价
### 数据集handwritten_digits_data  
SpectralClustering< MeanShift< AffinityPropagation< kmeans< AgglomerativeClustering< DBSCAN=GaussianMixture  
### 数据集text_documents  
SpectralClustering< DBSCAN< MeanShift<  K-Means< AffinityPropagation< GaussianMixture=AgglomerativeClustering
## NMI评价
### 数据集handwritten_digits_data  
SpectralClustering< MeanShift< DBSCAN= GaussianMixture< kmeans< AffinityPropagation< AgglomerativeClustering
### 数据集text_documents  
AgglomerativeClustering=GaussianMixture< SpectralClustering< MeanShift< DBSCAN< K-Means< AffinityPropagation
