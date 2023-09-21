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

#### Symmetric Matrixes
A matrix is considered symmetric if $\ A = A^T$

Given a matrix $\ A$ $\ AA^T$ is generally symmetric.

##### Simple proof problem that might be in the test on previous point

Proved that Given a matrix $\ A$ $\ AA^T$ is symmetric.

If $\ AA^T$ is symmetric then

$$\begin{equation}
AA^T = (AA^T)^T
\end{equation}$$

Applying properties of tranpose number 4 from above on the right hand side (RHS)

$$\begin{equation}
\begin{matrix}
RHS \rightarrow (AA^T)^T \\
(AA^T)^T = (A^T)^T A^T \\
\end{matrix}
\end{equation}$$

Applying properties of tranpose number 1 further

$$\begin{equation}
(A^T)^T = A
\end{equation}$$

subsitute and obtain:

$$\begin{equation}
AA^T = AA^T
\end{equation}$$

Therefore $\ AA^T$ is symmetric.

##### Proof on properties number 2 using induction

*equation*

$$\begin{equation}
(A_1 + A_2 + A_3 + ... + A_n)^T = A_1^T + A_2^T + A_3^T + ... + A_n^T 
\end{equation}$$

Assume the equation is true until $\ n=k$

$$\begin{equation}
(A_1 + A_2 + A_3 + ... + A_k)^T = A_1^T + A_2^T + A_3^T + ... + A_k^T 
\end{equation}$$

At $\ n=k+1$ the left hand side would be

$$\begin{equation}
((A_1 + A_2 + A_3 + ... + A_k) + A_{k+1})^T
\end{equation}$$
