# High-Dimensional-Data-and-Linear-Regression
Part I a): Points in High Dimensional Space
You will empirically verify what happens to the "center" of the space, and what happens at the "boundary".

Randomly generate n=100,000 points in d dimensions, sampled uniformly in the range [−1,1] for each dimension, where d
d will be varied from d=2 to d=20. That is, these points will be within the length l=2 hypercube in d dimensions.

First, find and plot the fraction of points that lie in the largest inscribed hypersphere within the above hypercube, as a function of d. Describe the trend.

Next, given ϵ=0.1, find and plot the fraction of points that lie within the ϵ width region along the boundary of the hypercube, as a function of d. Describe the trend.

Part I b): High Dimensional Normal Distribution
You will empirically verify what happens to the high dimensional normal distribution in terms of the distance of points from the center.

Randomly sample n=10,000 points from the standard multivariate normal distribution in d dimensions, where d=10,50,100,500. You may use np.random.multivariate_normal to generate this sample.

Plot the histogram of distances of points to the center of the space in d dimensions. Verify that for all d, the means distance of points to the center in d dimensions is d√d and the standard deviation is 1/2–√1/2.

Part II: Linear Regression via QR Factorization
Download the Wine Quality Dataset from the UCI Machine Learning repository. Extract the winequality-red.csv datafile that records 12 attributes about 1599 instances of red wine. You should parse and store the data as a data matrix, using the last "quality" attribute as the dependent or target variable Y, and first 11 attributes as the independent attributes/variables, X.

Implement the linear regression algorithm via QR factorization, namely Algorithm 23.1 on page 602 in Chapter 23. Make sure you augment X by adding a columns of ones as the first dimension.

You must implement QR factorization on your own, as described in Section 23.3.1 (you cannot use numpy.linalg.qr or similar function, though you may use it to verify your results).

Next, using the Q and the R matrices, you must solve for the augmented weight vector w. CSCI4390 can use numpy.linalg.inv for your solution, but CSCI6390 must implement backsolve via backsubstitution on their own without using the inv function. See Example 23.4 on how backsolve works.

After you have computed the weight vector w, print it, and then compute the SSE value and the R^2statistic, where:
R^2=TSS−SSE / TSS
where TSS is the total scatter of the response variable TSS=∑ni=1(yi−μY)2
