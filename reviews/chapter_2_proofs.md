# Chapter 2. Matrices Proofs

This section contains proofs on subsections of chapter 2. 

## Chapter 2.2 Properties of Matrix Operations

***

### Matrix Transpose Symmetry

Prove that Given a matrix $\ A$ $\ AA^T$ is symmetric.

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

***

### Matrix Transpose association

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

Using properties number 2.

$$\begin{equation}
((A_1 + A_2 + A_3 + ... + A_k) + A_{k+1})^T = (A_1 + A_2 + A_3 + ... + A_k)^T + A_{k+1}^T
\end{equation}$$

Subsituting from  $\ n=k$

$$\begin{equation}
(A_1 + A_2 + A_3 + ... + A_k)^T + A_{k+1}^T =  A_1^T + A_2^T + A_3^T + ... + A_k^T + A_{k+1}^T 
\end{equation}$$

Therefore

$$\begin{equation}
(A_1 + A_2 + A_3 + ... + A_k + A_{k+1})^T=  A_1^T + A_2^T + A_3^T + ... + A_k^T + A_{k+1}^T 
\end{equation}$$

which makes our initial equation true.

***

## Chapter 2.4 Inverse Matrices

***

### Using Inverse Matrix to Solve a System of Equations

If matrix $\ A$ invertible and $\ Ax = b$ then:

Multiply both side by  $\ A^{-1}$ to obtain:

$\ A^{-1}Ax =A^{-1} b$

since $\ A^{-1}A = I_A$

$\ x =A^{-1} b$


### Prove that given an invertible matrix $\ A$, $\ A^{-1}$ is unique

Proof by contradiction

1. Assume $\ A^{-1}$ is not unique: $\ A^{-1} = B$ and $\ A^{-1} = C$

2. Therefore: $\ AB = I = BA$ and $\ AC = I = CA$ *inverse matrix properties $\ AA^{-1} = I = A^{-1}A$*

3. Taking left hand side of both equations:

$\ AB = I$ and $\ AC = I$ multiply $\ C$ and $\ B$ to them respectively using the properties of identity matrix:

$\ CAB = CI$ and $\ BAC = BI$ 

4. Substituting from 2. $\ (CA)B = CI$ and $\ (BA)C = BI$: $\ (I)B = CI$ and $\ (I)C = BI$

5. Resulting $\ IB = CI$ and $\ IC = BI$ which is: $\ B = C$ and $\ C = B$

Since 5. is false, assuptiom from 1. is also false 




