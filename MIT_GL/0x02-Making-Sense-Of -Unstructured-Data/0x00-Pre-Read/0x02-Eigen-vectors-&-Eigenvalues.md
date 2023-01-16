# Eigenvectors and Eigenvalues

- Consider that we have a vector **V** and a matrix **A**.

- If we multiply matrix **A** with vector **V**, we obtain a new, transformed vector.

![](https://olympus.mygreatlearning.com/courses/74508/files/4905828/preview?verifier=IsAXbgucuslwrafcmUFxZNDR52rJyeat5esUi2sn)

- The below figure shows that multiplying by the matrix **A** has scaled the vector **V** to a new vector, with a different magnitude and a slightly different direction.

![](https://olympus.mygreatlearning.com/courses/74508/files/4905829/preview?verifier=QDi1PvVqfOZrRCrwEMSooxlXsHTeLy1vlFcH2gp9)

- As we know, vectors have both a magnitude and a direction. The new vector AV seems to have a different direction as well as magnitude in comparison to the old vector **V**.

- In linear algebra, the operation above is known as a linear transformation. It is not only restricted to scaling - **linear transformations** can be used for flipping, rotating, shearing and other mathematical operations.

- Let’s now consider a different vector **V** and multiply it with the same matrix **A**:

![](https://olympus.mygreatlearning.com/courses/74508/files/4905830/preview?verifier=bRp3lcCaYUFTQGUhQr7CaKxMhzch83C8zHMeZC4Y)

- In this example, we notice that something different has happened.

- We see that in this instance, while the magnitude of the new vector is certainly different, its direction has not changed.

- These special vectors are known in linear algebra as **Eigenvectors**.

- As illustrated in the example above, given the corresponding matrix **A**, eigenvectors are directionally-invariant when multiplied with that matrix i.e. they don’t change their direction on multiplication with matrix **A** - they merely get scaled in terms of magnitude. The value with which the eigenvector gets scaled, is known as the Eigenvalue, denoted by the symbol lambda.

- In our example, the eigenvector is
  ![](https://olympus.mygreatlearning.com/equation_images/%255Cbinom%257B1%257D%257B1%257D%2520)
  nd the eigenvalue is 3.

- So to summarize, the eigenvector of a matrix is a vector whose direction does not change when a linear transformation (matrix multiplication) is performed on it.

- Mathematically, the equation is represented as:
  ![](https://olympus.mygreatlearning.com/courses/74508/files/4905831/preview?verifier=sJzxotn9KWEYLbIVBsUNEIePYnEwMkFbyzuoONaH)

  - **A** - Transformation matrix
  - **v** - Eigenvector
  - ![](https://olympus.mygreatlearning.com/courses/74508/files/4905832/preview?verifier=FsLzMx0ch6x4bwdHYNyKRbuly4tsgpwNxvNBgalk) - Eigenvalue

- Taking ![](https://olympus.mygreatlearning.com/courses/74508/files/4905833/preview?verifier=UKlBTf64e4lYuoy2g9EW5GOxFzPUSjeldpCd4h7Z) to the left side:

- Lambda is a scalar, so taking **v** out in common:
  ![](https://olympus.mygreatlearning.com/courses/74508/files/4905808/preview?verifier=VlyxCOCw9zbOKPZfBxfDktDiYPnwFqw7RiU10xCU)

- An eigenvector is a non-zero vector. So, v cannot be zero.

- Hence, to satisfy the right-hand side condition,
  ![](https://olympus.mygreatlearning.com/courses/74508/files/4905836/preview?verifier=Oknkch7vawV9j4XbcQQjyH01N6HjPJeJOsruinAE)
  needs to be zero.

- If we were to multiply by the [inverse](https://byjus.com/maths/inverse-matrix/) of the matrix on both sides:

![alt](https://olympus.mygreatlearning.com/courses/74508/files/4905809/preview?verifier=rFdcTdmfIRbsoto000OVJDlhPTbn9TDVf196Ek40)

- **Since the product of a matrix and its inverse is I (the identity matrix)**, equating the left and right sides, we get:
  ![](https://olympus.mygreatlearning.com/courses/74508/files/4905838/preview?verifier=Iwnyp895qyyRbAQIAchAxyDtLpBG9zvhOekhhD7U)

- This is contradictory, as we have mentioned above that the Eigenvector cannot be zero.

- So that means we cannot actually use the inverse of
  ![alt](https://olympus.mygreatlearning.com/courses/74508/files/4905836/preview?verifier=Oknkch7vawV9j4XbcQQjyH01N6HjPJeJOsruinAE)
  as it is not an invertible matrix.

- In linear algebra, if a matrix is not invertible then the determinant of the matrix is equal to zero.

- That means, we only need to solve the equation
  ![alt](https://olympus.mygreatlearning.com/courses/74508/files/4905839/preview?verifier=Xl2fjFjZhFDkNYLKEcc4o0NSS2zD6gQqCLUNYsyL)
  to get the eigenvalues and through them, the eigenvectors.

- Due to Numpy in Python, we do not need to perform these operations by hand. Numpy has functions to find the eigenvalues and eigenvectors of a matrix for us.

## Why are Eigenvectors important?

- The directional invariance of Eigenvectors turns out to be an incredibly important mathematical property, and is utilized by many applications - Principal Component Analysis (PCA), for example, is a highly popular data projection technique that can be used to reduce the dimensionality of a dataset and visualize it in lower dimensions.
- To understand the concept of Eigenvectors and Eigenvalues in some more detail, check out this video from 3 Blue 1 Brown:

## [Eigenvectors and Eigenvalues](https://www.youtube.com/watch?v=PFDu9oVAE-g)

- This video talks about Eigenvectors and Eigenvalues with the help of visual representations and an example.

- It includes the calculations that are needed to get these values, and how to interpret them.
