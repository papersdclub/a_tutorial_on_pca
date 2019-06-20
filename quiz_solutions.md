# Solutions to quiz on PCA 

One note about the quiz before you read the answers. Some answers were intentionally very similar, so that you pay attention to important detail. 
For most of the answers I gave the % of respondents that answered correctly. Current average is 59%, but I know that a few people took the quiz without looking at the paper. Unfortunately, I can't do anything about it.

And now the correct answeres: 

## Question 1. PCA is technique for…
The correct answers are **dimensionality reduction** (93.75%) and **feature extraction** (50%).

Incorrect answers: 
- Data augmentation (6.25%) is a different technique. 
- Variance normalization (0%) isn't relevant. We use variance, but we're not normalising it. Normalization is a different process.

## Question 2. When performing PCA, we want to: 

The correct answer is **find the most meaningful basis.** (50%) 

Incorrect answers: 
- Find orthogonal vectors (18.75%). Why: Imagine unit vectors along the axes x and y wich are orthogonal vectors. And image a points cloud stretched from origin to the top right corner. We're definitely not satisfied with x and y axis, but these are SOME orthogonal vectors. 
- Find the components of the dataset (12.5%). Why: what components? 
- Estimate the number of dimensions (18.75%). Why: we already know the number of dimensions. We might want to find the optimal number of principal components to use, but that’s a bit different. 

## Question 3: Every observation (sample) in the dataset can be represented as: 

The correct answer is: **linear combination of some basis vectors** (50%)

The keywords here are linear combination and basis vectors. The exact quote from the paper is 
as follows: 
>“From linear algebra we know that all measurement vectors form a linear combination of 
this set of unit length basis vectors.”

So, it's not just a set of some vectors (whether orthogonal or not) and not just some unit vectors (because basis vectors are also orthogonal)

## Question 4: We assume that the signal of interest is 

The correct answer is **along the direction with the largest variance** (75%)

This is the key idea of PCA - to find the basis such that it captures the direction of the largest variance. All other answers are incorrect. 

## Question 5: If the element c_{1,2} of the covariance matrix C is 114, what is the value of c_{2,1} and what is the meaning?

The correct answer is **114, covariance** (50%). 
Matrix C is symmetric, so c_{1,2} is equal to c_{2,1}

## Question 6: If p_1 and p_2 are both principal components vectors, what statements are correct about them?

The correct answers are **p_1 is orthogonal to p_2**(75%) and **variance along p_1 is larger than variance along p_2**(43.75%). 

Most of respondents selected the first correct answer, but didn’t select the second one. 
The algorithm described in the paper says that we first find a principal component with maximum variance, save 
it as p_1, then we find the second component with maximum variance… A more detailed discussion can be found 
[here](https://stats.stackexchange.com/questions/22569/pca-and-proportion-of-variance-explained)

## Question 7: One of the key ideas for solving PCA with eigenvalue decomposition is that a symmetric matrix can be diagonalized by an orthogonal matrix of its eigenvectors.

The correct answer is **True**(87.5%). It follows directly from the paper. 

## Question 8: PCA with SVD is based on the idea that any matrix can be decomposed into a product of orthogonal matrix, identity matrix and another orthogonal matrix.

The correct answer is **False** (18.75). The statement looks right, but there is a small detail that makes it false. Identity matrix. What we actually want here is diagonal matrix (it is similar to identity, but not restricted to only 1s on the diagonal). 

## Question 9: In the derivation of PCA with SVD we exploit one very important property of orthonormal matrices. If U is an orthonormal matrix, then the inverse of U is equal to:

The correct answer is **U_transpose** (62.5%). That’s simply a property of orthonormal matrices. See Appendix A.1 in the paper. 

## Question 10: When do we need kernel PCA? 

The correct answer is when we want to capture non-linearity in the data (50%). 
See the end of Discussion section in the paper. 

# Conclusion

I think everyone did great on the quiz.
Our brain works in a way, that we actually learn more when we make a mistake. So, 
if you took the quiz after reading the paper and without looking at the answers, you did great! You brain scored 100%. Congratulations!







