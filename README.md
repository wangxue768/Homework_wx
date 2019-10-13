# Homework_wx
## 运行结果  

### test_handwritten_digits_data.py  
n_digits: 10, 	 n_samples 1797, 	 n_features 64  
__________________________________________________________________________________
init	  	          time    	homo	    compl	    NMI  
kmeans            	0.48s   	0.602	    0.650	    0.626    
AffinityPropagation	14.37s	  0.932   	0.460	    0.655  
MeanShift	          18.34s  	0.014	    0.281	    0.063  
SpectralClustering	987.75s 	0.001   	0.271	    0.012  
AgglomerativeClustering	0.62s	0.758	    0.836   	0.797  
DBSCAN   	          0.76s     	0	      1.000   	0.375  
GaussianMixture     0.11s     	0     	1.000   	0.375  

----  



### test_text_documents.py  
K-Means done in 12.550s  
Homogeneity: 0.443  
Completeness: 0.464  
NMI: 0.453  

AffinityPropagation done in 139.311s  
Homogeneity: 0.517  
Completeness: 0.601  
NMI: 0.557  






## 评价
### 时间评价

### Homogeneity评价

### completeness评价

### NMI评价
