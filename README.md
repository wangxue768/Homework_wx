# Homework_wx
## 运行结果  

### handwritten_digits_data.py  
n_digits: 10, 	 n_samples 1797, 	 n_features 64  

init		time	inertia	homo	compl	v-meas	ARI	AMI	silhouette  
k-means++	0.79s	69432	0.602	0.650	0.625	0.465	0.621	0.146  
random   	0.67s	69694	0.669	0.710	0.689	0.553	0.686	0.147  

----
### test.py  
n_digits: 10, 	 n_samples 1797, 	 n_features 64  
__________________________________________________________________________________
init		time	homo	compl	NMI  
kmeans   	0.56s	0	0.650	0.626  
AffinityPropagation	11.20s	0	0.460	0.655  
MeanShift	12.40s	0	0.281	0.063  

----  
### text_documents.py  
Usage: text_documents.py [options]

Options:  
  -h, --help            show this help message and exit  
  --lsa=N_COMPONENTS    Preprocess documents with latent semantic analysis.
  --no-minibatch        Use ordinary k-means algorithm (in batch mode).  
  --no-idf              Disable Inverse Document Frequency feature weighting.  
  --use-hashing         Use a hashing feature vectorizer  
  --n-features=N_FEATURES
                        Maximum number of features (dimensions) to extract
                        from text.  
  --verbose             Print progress reports inside k-means algorithm.  
Loading 20 newsgroups dataset for categories:  
['alt.atheism', 'talk.religion.misc', 'comp.graphics', 'sci.space']
3387 documents  
4 categories  

Extracting features from the training dataset using a sparse vectorizer
done in 2.757078s  
n_samples: 3387, n_features: 10000

done in 17.662s

Homogeneity: 0.471  
Completeness: 0.493  
NMI: 0.482

