# Chapter 2. Matrices Proofs

This section contains proofs on subsections of chapter 2. 

## Chapter 2.2 Properties of Matrix Operations

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
