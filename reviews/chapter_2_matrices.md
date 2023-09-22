# Chapter 2. Matrices

Summary on matrices

**NOTE**: section 2.1. is skipped, because it's already explained in 1.2

**Test Section: #1**

#### Homework

Starting page 59: 13, 28, 31, 38, 44, 57


## Chapter 2.2 Properties of Matrix Operations

#### Properties of Matrix Addition and Scalar Multiplication

1. $\ A + B = B + A$ Communtative properties of addition
2. $\ A + (B + C) = (A + B) + C$ Associative properties of addition
3. $\ (cd)A = c(dA)$ Associate properties of multiplication
4. $\ IA = A$ Multiplicative Identity $\ I$ is an identity matrix (more on that later)
5. $\ c(A + B) = cA + cB$ Distributive property
6. $\ (c + d)A = cA + dA$ Distributive property

#### Properties of Zero Matrix

A zero matrix $\ O$ or $\ O_{mn}$ is a matrix filled with zeros with a given dimesion. 
It usually assumes the size necessary for the calculation. 

in python with numpy: np.zeros((m, n))

1. $\ A + O = A$
2. $\ A + (-A) = O$ Associative properties of addition
3. if $\ cA = O$ then  $\ c = 0$  or $\ A = O$

#### Properties of Matrix Multiplication

Given matrices $\ A, B, C$ with appropriate size

1. $\ A(BC) = (AB)C$ Associative properties of matrix multiplication
2. $\ A(B + C) = AB + AC$ Distributive property
3. $\ (A + B)C = AC + BC$ Distributive property
4. $\ c(AB) = (cA)B = A(cB)$
  
#### Properties of Identity Matrix
An identity matrix of matrix $\ A_{m, n}$ is a square matrix of an appropriate size with the main diagonal of the matrix as ones and rest as zeros.

1. $\ AI_n = A$ 
2. $\ I_mA = A$

$$\begin{equation} I_n =
\begin{bmatrix}
1_{11} && 0 && 0 && ... && 0 && 0\\
0 && 1 && 0 &&... && 0 && 0\\
...n-2 row\\
0 && 0 && 0 &&... && 1 && 0\\
0 && 0 && 0 && ... && 0 && 1_{nn}\\
\end{bmatrix}
\end{equation}$$

#### Properties of Tranpose

1. $\ (A^T)^T = A$ 
2. $\ (A + B)^T = A^T + B^T$
3. $\ (cA)^T = c(A^T)$
4. $\ (AB)^T = B^T A^T$ # note change in multiplication order

### Symmetric Matrixes
A matrix is considered symmetric if $\ A = A^T$

Given a matrix $\ A$ $\ AA^T$ is generally symmetric.


## Chapter 2.3 Inverse of Matrix

A square matrix of size n by n $\ A$ is **invertible** (or **nonsingular**) when there exist such matrix $\ B$ that:

$$\begin{equation}
AB = BA = I_n
\end{equation}$$

Then the matrix $\ B$ is an inverse of $\ A$.

The inverse of $\ A$ can be denoted as $\ A^{-1}$.

#### Theorem

If $\ A$ is an invertible matrix ., then its inverse $\ A^{-1}$ is unique. 

### Finding the Inverse Matrix

To solve for an inverse of the matrix, form an **adjoined** matrix of the matrix $\ A$ and its identity matrix to form a coefficient matrix.
Then solve until the $\ A$ side of the adjoin matrix forms the $\ I$. The new value where **adjoined** $\ I$ is the $\ A^{-1}$.

Finding the inverse $\ A^{-1}$ given $\ A$:

$$\begin{equation}
A =
\begin{bmatrix}
1 && 4 \\
-1 && -3 \\
\end{bmatrix}
\end{equation}$$

Form **adjoined** matrix

$$\begin{equation}
\begin{bmatrix}
1 && 4 && 1 && 0 \\
-1 && -3 && 0 && 1 \\
\end{bmatrix}
\end{equation}$$

Solve with 

$$\begin{equation}
R_2 + R_1 \rightarrow R_{2new} =  
\begin{bmatrix}
1 && 4 && 1 && 0 \\
0 && 1 && 1 && 1 \\
\end{bmatrix}
\end{equation}$$

$$\begin{equation}
R_1 + (-4)R_2 \rightarrow R_{1new} =  
\begin{bmatrix}
1 && 0 && -3 && -4 \\
0 && 1 && 1 && 1 \\
\end{bmatrix}
\end{equation}$$

The resulting matrix is an **adjoined matrix** of $\ I_A$ and $\ A^{-1}$

$$\begin{equation}
A^{-1} =  
\begin{bmatrix}
-3 && -4 \\
 1 && 1 \\
\end{bmatrix}
\end{equation}$$

### Singular Matrices

Matrix $\ A$ is considered singular if non-inversible. 

Consider:

$$\begin{equation}
A =
\begin{bmatrix}
1 && 2 && 0\\
3 && -1 && 2\\
-2 && 3 && -2\\
\end{bmatrix}
\end{equation}$$

Trying to solve with **adjoined form**:

$$\begin{bmatrix}
1 && 2 && 0 && 1 && 0 && 0\\
3 && -1 && 2 && 0 && 1 && 0\\
-2 && 3 && -2 && 0 && 0 && 1\\
\end{bmatrix}$$

$$\begin{bmatrix}
1 && 2 && 0 && 1 && 0 && 0\\
0 && -7 && 2 && -3 && 1 && 0\\
0 && 0 && 0 && -1 && 1 && 1\\
\end{bmatrix}$$

The system is inconsistent, and there is no inverse. The matrix $\ A$ is singular.

#### Fast way of calculating the inverse of a 2x2 matrix

Given Matrix $\ A$

$$\begin{equation}
A =
\begin{bmatrix}
a && b \\
c && d \\
\end{bmatrix}
\end{equation}$$

Given Matrix $\ A^{-1}$ is:

$$\begin{equation}
A^{-1} = \frac{1}{ad-bc}
\begin{bmatrix}
d && -b \\
-c && a \\
\end{bmatrix}
\end{equation}$$


#### Properties of Inverse Matrices

Only square matrices can be inverted.

1. $\ (A^{-1})^{-1} = A$ 
2. $\ (A^k)^T = A^{-1}A^T A^{-1}A^T A^{-1}A^T .... = (A^{-1})^T$
3. $\ (cA)^{-1} = \frac{1}{c}A^{-1}$ Note the inverse of the constant
4. $\ (A^T)^{-1} = (A^{-1})^T$

If matrices $\ A$, $\ B$ are invertible matrices with order of $\ n$, then $\ AB$ is inversible and $\ (AB)^{-1} = B^{-1}A^{-1}$ note the similarity with transposition.

Invertible matrices also has cancellation properties. Given an invertible matrix $\ C$

1.  if $\ AC = BC$ then $\ A = B$ 
2.  if $\ CA = CB$ then $\ A = B$

Also

$\ AA^{-1} = I = A^{-1}A$

Note that it covers both side of matrix multiplication.

Given an invertible matrix $\ A$, $\ A^{-1}$ is unique.



### Using Inverse Matrix to Solve a System of Equations

If matrix $\ A$ invertible and $\ Ax = b$ then: $\ x =A^{-1} b$

### Elementary Matrcies

An elementary **row** operation is considered as one of the following:

1. non-zero scalar multiplication to a row
2. add or subtracking rows or a non-zero scalar multiple of a row
  - similar to a single operation during Gauss-Jordan elimination
4. interchage between 2 rows

A **matrix** is considered an **elementary** matrix when it is an n by n square matrix that can be obtained by a **single** elementary **row** operation from an identity matrix $\ I$ with a degree of n
