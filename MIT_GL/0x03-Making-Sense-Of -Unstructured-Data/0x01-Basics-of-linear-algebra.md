# Basics of Linear Algebra

## Matrix and Vectors

- To understand machine learning in-depth, let us first understand a few topics related to linear algebra. You do not necessarily need to understand linear algebra in-depth, to get started with machine learning. However, it will be useful in understanding the mathematics behind machine learning algorithms.

- In linear algebra, data is mostly represented using matrices and vectors.

## Matrix

- Matrices (plural of matrix) are used throughout machine learning algorithms, specifically for input variables, i.e., the variables we try to understand in machine learning. A matrix of size LaTeX: m\times n is a two-dimensional array that has m rows and n columns.

## Vector

- A vector is a one-dimensional array that has only one row - called a row vector, or just one column, also called a column vector.

- For example, in the below figure, X is a matrix with 3 rows and 2 columns, while Y is a simple column vector.

![](https://olympus.mygreatlearning.com/courses/74508/files/4905856/preview?verifier=TbcIQq6vWpWCIx6EN9o0rDuz6uhlOCrlc7L7PRB2)

- Now, let’s look at some operations that can be applied to vectors and matrices.

## Addition and Subtraction

- For the addition and subtraction of two vectors or two matrices, both should be of the same size. The addition and subtraction operations are performed in an "element-wise" manner between the two objects - that is, the corresponding elements from the two vectors or matrices are added to each other or subtracted from each other.

- For example, the below figure shows the addition and subtraction of two column vectors, each having 3 elements.

![](https://olympus.mygreatlearning.com/courses/74508/files/4905857/preview?verifier=jKha9qjhzThx4fTy1a5NnK1ZWq7w1xX82m2Wjoc2)

- This kind of "element-wise" addition and subtraction can similarly be performed for two or more matrices of the same size as well.

## Multiplying a matrix with a vector

- To multiply a matrix with a column (or row) vector, the matrix must have the same number of columns (or rows) as the number of elements in the column (or row) vector.
