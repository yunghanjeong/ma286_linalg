# Chapter 1. System of Linear Equations

Review for MAT286 Linear Algebra 

**Test Section: #1**

#### Homework

Starting page 22: 33, 35, 37, 43


## Chapter 1.1 Introduction to System of Linear Equations

Recall univariate linear equation: $\ y = mx + b $

which can also be written as: $\ a_1x + a_2y = b $

similarly: $\ a_1x_1 + a_2x_2 = b $

thus a linear equation with n variables can be written as

$\ a_1x_1 + a_2x_2 + ... + a_nx_n = b $

#### Definitions
$\ a_1, a_2,... a_n$ are known as **coefficients** and consist of real numbers

$\ b$ is a costant, a real number

$\ x_1, x_2,... x_n$ are known as **variables**

$\ a_1, x_1$ are known as **leading** coeffeicient and variables, respectively

### System of Linear Equations

A system of linear equations or a linear system of m equations and n varible is represented as:

$$\\begin{matrix}
a_{11}x_1 + a_{12}x_2 + ... + a_{1n}x_n = b_1\\
a_{21}x_1 + a_{22}x_2 + ... + a_{2n}x_n = b_2\\
...\\
a_{m1}x_1 + a_{m2}x_2 + ... + a_{mn}x_n = b_m\\
\end{matrix}$$

Any system of equations can be solved, finding the values of the variables. This value is the intersection points  of the lines (equations). In a system of equations you can have no solutions (no intersection or parallel lines), infinite amount of solutions (intersect at a line or greater), or a unique solution. For infinite amount of solutions there is always a trivial solution where everythings is equal to 0. 

## Chapter 1.2 Gaussian Elimination and Gauss-Jordan Elimination

A system of linear equations can be matricized as following:

$$\begin{bmatrix}
a_{11}, a_{12}, ... a_{1n}\\
a_{21}, a_{22}, ... a_{2n}\\
...\\
a_{m1}, a_{m2}, ... a_{mn}\\
\end{bmatrix}
\begin{bmatrix}
x_1\\
x_2\\
...\\
x_n\\
\end{bmatrix}=
\begin{bmatrix}
b_1\\
b_2\\
...\\
b_n\\
\end{bmatrix}$$

or simply

$\ AX = b$

#### Definitions
$\ A$ is the **coefficient matrix** and consist of real numbers

$\ X$ is the variable matrix consisting of elements $\ x_1, x_2,... x_n$ as a column matrix (vector)

$\ b$ is a matrix constisting of real number constants

### Solving a system of linear equations

A system of linear equation can be represented as an augmented matrix.

Given following system:

$$\begin{matrix}
x && -2y && +3z && = 9\\
-x && +3y && && = -4\\
2x && -5y && +5z && = 17\\
\end{matrix}$$

matricized as:

$$\begin{bmatrix}
1 && -2 && 3\\
-1 && 3 && 0\\
2 && -5 && 5\\
\end{bmatrix}
\begin{bmatrix}
x\\
y\\
z\\
\end{bmatrix}=
\begin{bmatrix}
9\\
-4\\
17\\
\end{bmatrix}$$

combine the **coefficient matrix** and the **constants** and form an **augmented matrix**:

$$\begin{bmatrix}
1 && -2 && 3 && 9\\
-1 && 3 && 0 && -4\\
2 && -5 && 5 && 17\\
\end{bmatrix}$$

This augmented matrix can be formatted in to **Row-Echelon Form** with looks for leading 1 and 0's under all leading 1's.
Rows are represented as **R** with subscripting denoting their positions for calculation.

Row 1 already has a leading 1. Obtain leading 1 and 0 for row 2:

$$\begin{equation} R_{2new} = R_2+R_1 \rightarrow 
\begin{bmatrix}
1 && -2 && 3 && 9\\
0 && 1 && 3 && 5\\
2 && -5 && 5 && 17\\
\end{bmatrix}
\end{equation}$$

Continuing on row 3 to obtain leading 0's. Note keeping consistent notation by limiting calculation with sum and multiplying by negative can lower errors. 

$$\begin{equation} R_{3new} = R_3 + (-2)(R_1) \rightarrow 
\begin{bmatrix}
1 && -2 && 3 && 9\\
0 && 1 && 3 && 5\\
0 && -1 && -1 && -1\\
\end{bmatrix}
\end{equation}$$

$$\begin{equation} R_{3new} = R_3 + R_2 \rightarrow 
\begin{bmatrix}
1 && -2 && 3 && 9\\
0 && 1 && 3 && 5\\
0 && 0 && 2 && 4\\
\end{bmatrix}
\end{equation}$$

$$\begin{equation} R_{3new} = R_3 * \frac{1}{2} \rightarrow 
\begin{bmatrix}
1 && -2 && 3 && 9\\
0 && 1 && 3 && 5\\
0 && 0 && 1 && 2\\
\end{bmatrix}
\end{equation}$$

From row 3 we can gather that $\ z = 2$.

Back substitute to obation following from row 2: $\ y + 3(2) = 5$, $\ y = -1$.

Repeat on row 1. : $\ x -2(-1) + 3(2) = 9$, $\ x = 1$

Solution can be written as **(1, -1, 2)**


### Gauss-Jordan Elimination and Reduced Row-Echelon Form

Reduced row-echelon form is row-echolon forms but with zeros on top of the leading ones. 

It will have identity matrix like look, but does not have to be.

Carrying on the matrix from above:

$$\begin{bmatrix}
1 && -2 && 3 && 9\\
0 && 1 && 3 && 5\\
0 && 0 && 1 && 2\\
\end{bmatrix}$$

Using the known variable $\ z$ to create zeros above leading ones

$$\begin{equation} R_{2new} = R_2 + (-3)R_3 \rightarrow 
\begin{bmatrix}
1 && -2 && 3 && 9\\
0 && 1 && 0 && -1\\
0 && 0 && 1 && 2\\
\end{bmatrix}
\end{equation}$$

$$\begin{equation} R_{1new} = R_1 + (-3)R_3 \rightarrow 
\begin{bmatrix}
1 && -2 && 0 && 3\\
0 && 1 && 0 && -1\\
0 && 0 && 1 && 2\\
\end{bmatrix}
\end{equation}$$

Finally using row 2.

$$\begin{equation} R_{1new} = R_1 + 2R_2 \rightarrow 
\begin{bmatrix}
1 && 0 && 0 && 1\\
0 && 1 && 0 && -1\\
0 && 0 && 1 && 2\\
\end{bmatrix}
\end{equation}$$

The final column, constants, are the solution to your equation.

#### System with no solutions
Consider the following system, usually obtained during Gauss-Jordan elimination process:

$$\begin{bmatrix}
1 && -2 && 3 && 4\\
0 && 1 && 1 && 1\\
0 && 0 && 0 && 2\\
\end{bmatrix}$$

Row 3 indicates $\ 0 = 2$ which is a false statement. In this case there is no solution and the system is considered **inconsistent**

#### Homogenous Equations 
A system is considered homogenous if all the constant is a zero column matrix.

Example:

$$\begin{bmatrix}
-1 && 3 && 2 && 0\\
4 && 1 && 1 && 0\\
2 && 7 && 4 && 0\\
\end{bmatrix}$$

A homogenous system of equation always has a trivial answer where all the variables are 0. 

#### System with infinite solutions
If a system equation intersect at a line (or plane ...) there are infinitely many solutions. To represented the solution must be parameterized.

Consider the following row-echelon matrix

$$\begin{bmatrix}
1 && 0 && 4 && 4\\
0 && 1 && 1 && 1\\
0 && 0 && 0 && 0\\
\end{bmatrix}$$

Row 3 indicates $\ 0 = 0$ which is a true statement. In addition solving for variable 3 we can obtain the solution for the rest of the equation. Therefore we will variable 3 as the free variable.

$$\begin{matrix}
x_3 = t\\
x_2 + t = 1\\
x_2 = 1 - t\\
x_1 + 4t = 8\\
x_1 = 8 - 4t\\
x_1 = 4(2 - t)\\
\end{matrix}$$

The solution: $\ (4(2-t), 1-t, t) $

There may be systems that require more than 1 free variable. 




