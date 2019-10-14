# Homework_wx
## 运行结果  

### test_handwritten_digits_data.py  
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

### test_text_documents.py  
K-Means done in 7.730s  
Homogeneity: 0.485   
Completeness: 0.571  
NMI: 0.526  

AffinityPropagation done in 73.955s  
Homogeneity: 0.517  
Completeness: 0.601  
NMI: 0.557   






## 评价
### 时间评价
#### 数据集handwritten_digits_data
GaussianMixture< kmeans< AgglomerativeClustering< DBSCAN< AffinityPropagation< MeanShift< SpectralClustering
#### 数据集text_documents  

### Homogeneity评价

### completeness评价

### NMI评价
