# Discussion 

### 1. Summary of PCA paper
The question that PCA asks is `Is there another basis which is a linear combination of the original basis that best re-expresses our dataset?` (It is quoted from the paper but I think it best expresses what the analysis does) --@Sarah Majors 

PCA stands for principal component analysis is a standard tool in modern data analysis because it is a simple, non-parametric method for extracting relevant information from confusing data sets. --@Marce

### 2. Can anyone explain why eigenvectors play an important role in calculating PCA?
From my understanding they are really important because they will let us find the golden matrix for change basis, based on our X matrix. --@marce

Eigenvectors create a orthogonal basis, which can represent our data in much better way and remove redundant dimensions. --@dharmendra 

### 3. What is more efficient? SVD or eigendecomposition?

Both are numerically same. But some people says SVD is better due to its implementation. [Why does Andrew NG prefer SVD and not EIG of covariance matrix to PCA ?](https://stats.stackexchange.com/questions/314046/why-does-andrew-ng-prefer-to-use-svd-and-not-eig-of-covariance-matrix-to-do-pca) --@dharmendra

### 4. Is it necessary to do feature normalization before PCA and why?
Yes, I believe it is best that you normalize. Otherwise, features with considerably larger ranges could influence too much the results and you would end up with a biased final result. --@Artur Freitas Gonçalves

### 5. Is it necessary to have target variable for applying dimenionality reduction algorithms?
Target variable is not required for PCA and SVD --@dharmendra

### 6. In the change of basis section, we have PX = Y, where P is stated to be a linear transformation applied to X. It's then stated that this equation can have many interpretations, one of which is that - Geometrically, P is a rotation and a stretch which again transforms X into Y. How exactly is that interpretation made? P is shown to be just a column vector, and if I'm not wrong, a column vector can't be a rotation and a stretch, right? So, how did they come to that conclusion?
Every matrix multiplication can be represnted as  a transformation in the space. Refer to [this link](https://www.youtube.com/watch?v=kYB8IZa5AuE&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=3) --@shivu

### 7. When should we choose PCA over algorithms like linear regression?
They have different goals, PCA is intended to reduce dimensions of a dataset, and it is unsupervised, you don't need to give labels. In linear regression, you want to predict specific labels. --@Diego

### 8. In figure 2, it is stated - Note that the largest direction of variance does not lie along the basis of the recording, but rather along the best-fit line. What exactly is the significance of this statement?
The basis of the recording is our well known `x-y`, so the figure is an affirmation that there is another basis that represents better our data. --@marce

### 9. In the section related to redundancy, is redundancy something inherently expected? They provided 3 examples of different redundancies we could face, but those are based on measurements being made (r1 and r2). They claim that when there's high-redundancy we don't require 2 responses, only 1 is enough and so the number of sensor recordings can be reduced. But, we can only find out that there is low or high redundancy after we have some set of measurements from the sensors. Are they saying that high redundancy is expected because we have more sensors or are they saying we get some measurements, look at the possible redundancies and then reduce sensor recordings? Not super clear on the process behind this bit because we can't know in advance how many sensor recordings would cause how much redundancy, right?
It could be because multiple sensors are giving the same data.  Products tend to be over-built and may give redundant data.  Another way redundant data can happen is if you have combined multiple data sets.  Or if the project has gotten too big and people are just adding data without really checking what is already there. --@Sarah Majors 

### 10. Can i use LIME( a tool used for explaining AI models) after using PCA?
We can still use LIME, but now the analysis will be done on the new features we get after applying PCA. If the features in the original dataset were known variables, then this analysis wouldn't help as we don't know what PCA features actually represent in the real world. But if the features in original dataset were anonymised, then we can just present the analysis in terms of PCA features. --@Abhishek Tandon 

### 11. Can anyone explain about kernel PCA?
I am not sure of the mathematics here, but what I understood was that, we can apply the kernel trick used in SVM to first convert the features into an infinite dimensional space (applying kernel function on features) and then doing normal PCA on these transformed features. This allows for removing high non linearities in the dataset. A formulation in PCA is that we can recover an approximation to the dataset and analyse how the PCA algorithm is performing by measuring the distance between original samples and the reconstructed samples, called the reconstruction error. Using kernel PCA, we cannot recover the dataset to measure this reconstruction error. One drawback of this algorithm. scikit learn library provides an approximation so that we can calculate the reconstruction error even in case of kernel PCA. --@Abhishek Tandon 

### 12. Do we need to apply PCA while working with random forests ? Because as random forests are tough to overfit I think they can overcome the curse of dimensionality
But considering a dataset where there are many many features, let's say more than 5000 features, then in those cases it would be better if apply PCA or other dimensionality reduction techniques so that we can speed up training. In case of random forests or decision trees, the greater the number of features the more chances are there for a tree with a huge depth and convoluted boundaries, so to deal with that issue also PCA might help --@Abhishek Tandon 

### 13. In the paper, they use a trick where they select the P matrix to be a matrix where each row is an eigenvector of (XX_trans)/n. So, generic math question - Is this like a well known trick? If not, how do you think someone would go about incorporating something like this while doing research of their own? I am not quite sure of the significance of this trick (going through this again, and the appendix too, to understand better) because then the question becomes - what happens if each row of P is NOT an eigenvector, does PCA start to fail or there is some more math needed to solve it or it is an assumption without which PCA wouldn't work at all?
I think first we calculate covariance matrix of features, then we calculate eigen vectors(rows of P) of covariance matrix , so P will always be a matrix of eigenvectors. --@shivu

### 14. Why did PCA fail for the fig 6(b) on page 9 though?
Figure 6: Non-Gaussian distributed data causes PCA to fail. In exponentially distributed data the axes with the largest variance do not correspond to the underlying basis. One of assumption for PCA is data distribution will be gaussian and based on that only we calculate signal to noise ratio. For other distributions high variance wouldn't mean high SNR. [How to check if a data is in gaussian distribution in R or excel?](https://datascience.stackexchange.com/questions/14997/how-to-check-if-a-data-is-in-gaussian-distribution-in-r-or-excel) --@dharmendra 
