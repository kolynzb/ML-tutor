2. Is the purpose of Dimensionality Reduction for clustering to better visualize multi-dimensional data? Do we use the results of PCA and Principal Components to remove the least effective dimensions to improve clustering?
Tags: #dimensionality_reduction #pca #visualization #clustering

Ans: Dimensionality reduction is beneficial in numerous ways. For starters, it aids in the visualization of multidimensional data because reducing the dimensionality to a few dimensions (e.g., 2 or 3 dimensions) allows for much better visualization of the samples. As a result, it can be used to extract insights from data (e.g. detect clusters and identify outliers). Second, fewer dimensions result in less computation time. Dimensionality reduction is also useful because some algorithms do not perform well when the dimensions are large.

This is entirely dependent on the available data. If the dataset has very few features in comparison to the number of samples, then reducing the number of features is probably not necessary. If the number of features is greater than the number of samples, the "curse of dimensionality" will occur, and the K-means algorithm will not produce good results. We might want to reduce the number of features in this case. So, if the data is very high dimensional, PCA can be used first before applying K-means.

 

3. How do you handle categorical features for clustering using K-means?
Tags: #categorical_features #one-hot-encoding #kmodes #kmeans

Ans: As K-means clustering is not directly applicable to categorical data, we have to turn categorical data into numerical. We can use one-hot-encoding as one way to try to do that.

N.B: Using one-hot encoding on categorical variables is a good idea when the categories are equidistant from each other (features are considered equidistant when they are not related to one another i.e they cannot be ordered). So a color variable with values such as green, red, blue etc. may be a suitable scenario for this. However, if for instance you have colors such as light blue, dark blue and yellow, using one-hot encoding might not give you the best results since dark blue and light blue are likely "closer" to each other than they are to yellow.

In case categorical values are not "equidistant" and can be ordered, you could also give the categories a numerical value. For instance, kids, teenagers, and adults could potentially be represented as 0, 1, and 2. This would make sense because a kid is "closer" to being a teenager than to being an adult.

You can also use K-modes for clustering categorical variables. It defines clusters based on the number of matching categories between data points. This is in contrast to the K-means algorithm, which clusters numerical data based on Euclidean distance.

Suppose your data contains both numeric and categorical variables. In that case, the best way to carry out clustering on the dataset is to create Principal Components of the dataset and use the Principal Component scores as inputs into the clustering. You can then do a separate PCA for the numerical and categorical variables, and use the combined results as input into your clustering.

 

4. Do we lose some information by doing PCA?
Tags: #information_loss #dimensions #pca #variance

Ans:  After implementing PCA on the dataset, your original features will turn into Principal Components. These Principal Components are linear combinations of your original features, and hence they are not as readable and interpretable as the original features themselves.

The goal of performing PCA is to reduce the dimensions while retaining the majority of the information. For example, suppose you run PCA on a 10-dimensional dataset and reduce it to two dimensions while retaining the majority of the variance in the dataset. However, reducing from ten to two dimensions will inevitably result in some information loss. 

For example, if we have 7 dimensions and we are reducing our dataset to 3 dimensions using PCA - let's assume this explains 90% of the variance in our dataset. That means we would lose information about the remaining 10% of the variance being explained by the original dataset. 

 

5. In the learning instrument ‘Notebook - Dimensionality Reduction’, are the results obtained from the following two approaches for generating Principal Components the same, or different?
Method 1:
# The components are 
print([i[0] for i in v])
print([i[2] for i in v])

Method 2:
# Printing the components 
print(pca.components_) 
Tags: #components #eigenvectors #eigenvalues

Ans:  Yes, the eigenvectors from both methods are the same.

In the first method, we take the eigenvectors with respect to the highest eigenvalues.

For example, if the eigenvalues are as given:

Eigenvalues: [ 1.77101346e+02  4.58319875e+01 -6.02110392e-15 -6.43438773e-16]

The first and second eigenvalues have greater values in this list.

So, when printing the eigenvectors, you must modify the code accordingly.

The updated code would be:

# The components are 
print([i[0] for i in v])
print([i[1] for i in v])
And, components_ mathematically represent the directions of maximum variance in the data. Equivalently, the right singular vectors of the centred input data are parallel to its eigenvectors. So, pca.components_ also gives us the same result as method 1.

 

6. In the case study ‘Socio-economic Factors for Geographic Clustering’,  when scaling the data, we have left out two lines: country and gross domestic product. But what happens if, after clustering, we want to know which countries are in every cluster?
Tags: #clustering #labels #countries

Ans: We can use the previous DataFrame, 'data', to update the K-means labels. Then we'll be able to tell which countries belong to each cluster.

 faq_1.PNG

 

 

7. Regarding the notebook 'Education Data Analysis': 
  a) PCA(n_components=n, random_state=1)
What does random_state mean here? 
     
b) data_pca = pd.DataFrame(np.round(pca.components_[:4,:],2),index=pc_comps,columns=data_scaled.columns)
Explain how the above code syntax was constructed.
Tags: #random_state #components #education_data_analysis

Ans: a) random_state =1, we add a random integer here for reproducible results across multiple function calls. Please refer to this documentation.

b) pca.components_[:4,:], here pca_components gives us the eigenvectors of the covariance matrix of the central input matrix. And we only take 4 Principal Components (i.e. 4 rows) and all the respective columns, that's why [:4, :] is used. Then we round it to 2 decimal places using np.round (pca.components_[:4,:], 2).

As we are creating a new DataFrame using the Principal Components, so we need to mention the index. And, the index is nothing but the name of the Principal Components i.e pc_comps = ['PC1','PC2','PC3','PC4']. So, we used, index=pc_comps.

Similarly, we mention the column names using columns=data_scaled.columns. So, here in this newly created DataFrame as well, columns will be the same as what was in the 'data_scaled' DataFrame.

 

8. In the 'Handout - Dimensionality Reduction', how do we get the second table which shows Pattern 1 and Pattern 2 as:
-1 +1 -1 +1    
    &
+1 +1 -1 -1  
respectively?
Tags: #pca #components #patterns #round_off

Ans: We get Pattern 1 and Pattern 2 from the PCA components itself.
But, if you look at the notebook, we have our components as:

[[-0.50806081 0.49180709 -0.49180709 0.50806081]
 [ 0.49180709 0.50806081 -0.50806081 -0.49180709]]
So, we have just rounded off the above value (i.e if the value >= 0 then we have taken 1, else -1), and that value is given in Pattern 1 and Pattern 2.

 

9. When should I use Gaussian Mixture Models vs. K-means for clustering data?
Tags: #gmm #kmeans #difference #shapes

Ans: K-means Clustering is well suited for roughly spherical clusters of equal size. It may fail if these conditions are violated (although it may still work if the clusters are very widely separated). And, we want the clusters to not overlap. 

GMMs can fit clusters with a greater variety of shapes and sizes. GMMs give a probabilistic assignment of points to clusters. This lets us quantify uncertainty. For example, if a point is near the 'border' between two clusters, it's often better to know that it has near equal membership probabilities for these clusters, rather than blindly assigning it to the nearest one.

A Gaussian Mixture will almost always fit better than K-means: the clustering will mimic the data cloud better and with a smaller K. K-means is useful primarily because it’s very fast, so might be more easily fit to very large data sets with large dimensions.