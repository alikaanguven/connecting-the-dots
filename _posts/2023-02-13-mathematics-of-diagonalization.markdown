---
layout: post
title:  "Mathematics of Diagonalization"
date:   2023-02-13 18:52:00 +0300
categories: jekyll update
---
### Summary for TL;DR community

$$
\begin{equation}
A = Q \Lambda Q^{-1}
\end{equation}
$$

1. If an $A_{n \times n}$ matrix has $n$ distinct eigenvalues:  

    $Q$ is the matrix where all the columns are eigenvectors of $A$, and $Q$ is invertible.  
    $\Lambda$ is a diagonal matrix with Complex eigenvalues of $A$ as its entries.  

2. If an $A_{n \times n}$ matrix is Real and symmetric:  

    $Q$ is the matrix where all the columns are eigenvectors of $A$, and $Q$ is orthogonal.  
    $\Lambda$ is a diagonal matrix with Real eigenvalues of $A$ as its entries.  

3. If an $A_{n \times n}$ matrix is Hermitian:

    $Q$ is the matrix where all the columns are eigenvectors of $A$, and $Q$ is unitary.  
    $\Lambda$ is a diagonal matrix with Real eigenvalues of $A$ as its entries.  

4. If an $A_{n \times n}$ matrix is normal:

    $Q$ is the matrix where all the columns are eigenvectors of $A$, and $Q$ is unitary.  
    $\Lambda$ is a diagonal matrix with Complex eigenvalues of $A$ as its entries.  
<br/><br/>
<br/><br/>
  
$$
\begin{equation}
M = L M_{diag} L^{\intercal}
\end{equation}
$$


* If an $M_{n \times n}$ matrix is Complex and symmetric (Autonne-Takagi):

    $M$ is a diagonal matrix with non-negative eigenvalues of $M^\dagger M$ as its entries.  
    The columns of $L$ are eigenvectors of $M M^\dagger$.  

$$
\begin{equation}
M = L M_{diag} R^{\dagger}
\end{equation}
$$

* If an $A_{m \times n}$ matrix is normal (SVD):

    $M$ is a diagonal matrix with non-negative eigenvalues of $A^\dagger A$ as its entries.  
    The columns of $L$ are eigenvectors of $M M^\dagger$.  
    The columns of $R$ are eigenvectors of $M^\dagger M$.

<br/><br/>
<br/><br/>

### SPECTRAL THEOREM


Spectral theorem is all about when and how a matrix can be diagonalized.  

**Q:** When is a matrix diagonalizable?  
**A:** Let's start by writing the eigenvalue problem in matrix form. Let $A$ be an $(n \times n)$ matrix, and $\lambda$ and $v$ represent the corresponding eigenvalues and eigenvectors.  

$$
\begin{align}
Av &= \lambda v \\
A Q &= \Lambda Q \\ \nonumber \\

A_{n \times n}

\begin{bmatrix}
    v_{11} & v_{21} & \dots & v_{n1} \\
    v_{12} & v_{22} & \dots & v_{n2} \\
    \vdots & \vdots & \ddots &  \\
    v_{1n} & v_{2n} &  & v_{nn} \\
\end{bmatrix}

&=

\begin{bmatrix}
    \lambda_{1} &  &  &  \\
        & \lambda_{2} &  &  \\
        &  & \ddots &  \\
        &  &  & \lambda_{n} \\
\end{bmatrix}


\begin{bmatrix}
    v_{11} & v_{21} & \dots & v_{n1} \\
    v_{12} & v_{22} & \dots & v_{n2} \\
    \vdots & \vdots & \ddots &  \\
    v_{1n} & v_{2n} &  & v_{nn} \\
\end{bmatrix}


\end{align}
$$

If $Q$ matrix is constructed to have eigenvectors of A as its columns, and $\Lambda$ is constructed in a way that is diagonal which is formed by the eigenvalues of $A$, then the eigenvalue problem is succefully expressed with matrices[$^{[1]}$](https://math.okstate.edu/people/binegar/3013-S99/3013-l16.pdf). At this point if $Q$ is assumed to be **invertible**, we can further deduce:

$$
\begin{equation}
A = Q \Lambda Q^{-1}
\label{diagonalization}
\end{equation}  
$$

However, we have to make sure that $Q$ is indeed invertible. If all the columns of $Q$ i.e. eigenvectors of $A$ are linearly independent, $Q$ has an inverse. Therefore $A$ must have $n$ eigenvalues associated with $n$ distinct eigenvectors [$^{[2]}$](https://math.berkeley.edu/~arash/54/notes/5_3.pdf). Another way to put this is to say "the algebraic multiplicities of each eigenvalue of $A$ should be equal to the geometric multiplicity".

The spectral theorem provides more information on some special cases.
* Cauchy formulated diagonalization for $$\mathbb{R}$$eal, and symmetric matrices.  
* von Neumann generalized the theory to Hermitian (self-adjoint) matrices, and normal matrices.  

<!-- 
Before we move on maybe it is beneficial to introduce another relation. Multiplying the right hand side of the 3<sup>rd</sup> equation by $x$.

$$
\begin{align}
Ax &= Q \Lambda Q^{-1} x \\


\end{align}
$$

 -->
  
<!-- Consider a linear map $A$ defined on a vector space $V$ equipped with an inner-product $\langle \cdot,\cdot \rangle$.

$$
\begin{align}
A&: \qquad V \rightarrow V \qquad V \in \mathbb{C}^{n} \\
\nonumber \\
\langle \cdot,\cdot \rangle&: V \times V \rightarrow K \quad \ \ \ K \in \mathbb{R}  \\
\end{align}
$$ -->

**Theorem states**  
If $$A$$ is Hermitian ($A^{\dagger}=A$) on some vector space $V$, then:

**1.** each eigenvalue of A is $$\mathbb{R}$$eal,      
**2.** there exists an orthonormal basis of $$V$$ consists of eigenvalues of $$A$$.  

**Proof of 1**  
Say $x$ is an eigenvector, and $\lambda$ is the corresponding eigenvalue of $A$. Then:

$$
\begin{align}
Ax &= \lambda x \\
\langle Ax, x \rangle &= \langle x, Ax \rangle \nonumber \\
\langle \lambda^{*} x, x \rangle &= \langle x, \lambda x \rangle  \nonumber \\
\lambda^{*} \langle x,x \rangle &= \lambda \langle x,x \rangle  \nonumber \\
\end{align}
$$

$$
\begin{equation}
\lambda^{*} = \lambda
\end{equation}
$$

**Proof of 2**  
We are trying to show that if A is Hermitian, eigenvectors to different eigenvalues are perpendicular[$^{[3]}$](https://people.math.harvard.edu/~knill/teaching/math22b2019/handouts/lecture17.pdf).


**Assume** two distinct eigenvalues ($\lambda \neq \mu$).

$$
\begin{align}

A v &= \lambda v \\
A w &= \mu w \\
\end{align}
$$

**Then:** 

$$
\begin{align}

\lambda \langle v | w \rangle &= \langle \lambda v | w \rangle = \lambda \langle A v | w \rangle \\
&= \langle v | A w \rangle = \lambda \langle v | \mu w \rangle \\
&= \mu \langle v | w \rangle \\
\end{align}
$$

**But:**  $\lambda \neq \mu$,  
**Then:** $\langle v | w \rangle = 0$ should be true. *Q.E.D.*

So far we have demonstrated that the eigenvalues of Hermitian matrices are Real, and eigenvectors for different eigenvalues are orthogonal, but these demonstrations are useful only for the diagonalization of matrices with a simple spectrum. Let's define what simple spectrum is.

**Definition:** If $A_{n \times n}$ is a matrix with all different eigenvalues, A is called to have a **simple spectrum**.

We can now proceed with proving the diagonalizability for any Hermitian matrix, but maybe it is beneficial to introduce one relation that we are going to use to prove it.

**Completeness relation:** is a mathematical trick that physicists use most often to decompose a vector into its components of the space. Let's, again, start with the eq. $\ref{diagonalization}$. Proving the eigenvectors are orthogonal for different eigenvalues of the matrix $A$, matrix $Q$ has now the ortogonal eigenvectors as its column. Remembering that orthonormal columns is a strict requirement for a unitary matrix, we understand that the matrix Q should be unitary[$^{[4]}$](https://math.stackexchange.com/questions/1688950/why-do-the-columns-of-a-unitary-matrix-form-an-orthonormal-basis) (**N.B.** If Q is both Real and unitary, it is an orthogonal matrix). **Thus**, $Q^{-1}=Q^{\dagger}$.

$$

A x = Q \Lambda Q^{-1} x \\\\

\begin{align}

    
    
     &= \begin{bmatrix}
        v_{11} & v_{21} & \dots & v_{n1} \\
        v_{12} & v_{22} & \dots & v_{n2} \\
        \vdots & \vdots & \ddots &  \\
        v_{1n} & v_{2n} &  & v_{nn} \\
    \end{bmatrix}
    
    \begin{bmatrix}
        \lambda_{1} &  &  &  \\
         & \lambda_{2} &  &  \\
         &  & \ddots &  \\
         &  &  & \lambda_{n} \\
    \end{bmatrix}
    
    \begin{bmatrix}
        v_{11}^{*} & v_{12}^{*} & \dots & v_{1n}^{*} \\
        v_{21}^{*} & v_{22}^{*} & \dots & v_{2n}^{*} \\
        \vdots & \vdots & \ddots &  \\
        v_{n1}^{*} & v_{n2}^{*} &  & v_{nn}^{*} \\
    \end{bmatrix}

    \begin{bmatrix}
    x_1 \\
    x_2 \\
    \vdots\\
    x_n
    \end{bmatrix} \nonumber \\ \nonumber \\


    &= \begin{bmatrix}
        v_{11} & v_{21} & \dots & v_{n1} \\
        v_{12} & v_{22} & \dots & v_{n2} \\
        \vdots & \vdots & \ddots &  \\
        v_{1n} & v_{2n} &  & v_{nn} \\
    \end{bmatrix}
    
    \begin{bmatrix}
        \lambda_{1} &  &  &  \\
         & \lambda_{2} &  &  \\
         &  & \ddots &  \\
         &  &  & \lambda_{n} \\
    \end{bmatrix}
    
    \begin{bmatrix}
        v_{1}^{\dagger} x \\
        v_{2}^{\dagger} x \\
        \vdots \\
        v_{n}^{\dagger} x 
    \end{bmatrix} \nonumber \\ \nonumber \\

    &= \begin{bmatrix}
        v_{11} & v_{21} & \dots & v_{n1} \\
        v_{12} & v_{22} & \dots & v_{n2} \\
        \vdots & \vdots & \ddots &  \\
        v_{1n} & v_{2n} &  & v_{nn} \\
    \end{bmatrix}
    
    \begin{bmatrix}
        \lambda_{1} v_{1}^{\dagger} x \\
        \lambda_{2} v_{2}^{\dagger} x \\
        \vdots \\
        \lambda_{n} v_{n}^{\dagger} x 
    \end{bmatrix} \nonumber \\ \nonumber \\

    &= \begin{bmatrix}
        v_{11} \lambda_{1} v_{1}^{\dagger} x  + v_{21} \lambda_{2} v_{2}^{\dagger} x + \dots + v_{n1} \lambda_{n} v_{n}^{\dagger} x \\
        v_{12} \lambda_{1} v_{1}^{\dagger} x  + v_{22} \lambda_{2} v_{2}^{\dagger} x + \dots + v_{n2} \lambda_{n} v_{n}^{\dagger} x \\
        \vdots \\
        v_{1n} \lambda_{1} v_{1}^{\dagger} x  + v_{2n} \lambda_{2} v_{2}^{\dagger} x + \dots + v_{nn} \lambda_{n} v_{n}^{\dagger} x \\
    \end{bmatrix} \label{relation_harvard} \\ \nonumber \\

    &= \sum_{k} v_{k} \lambda_{k} v_{k}^{\dagger} x = \sum_{k} \lambda_{k} v_{k} v_{k}^{\dagger} x \\\\
    
\end{align}
$$

$$
\begin{equation}
A = \sum_{k} \lambda_{k} v_{k} v_{k}^{\dagger}
  = \sum_{k} \lambda_{k} | v_{k} \rangle \langle v_{k}  |
\label{completeness}
\end{equation}
$$

This final equation $\ref{completeness}$ will be useful in the next proof. I anticipate there might be one single confusion with the equation $\ref{relation_harvard}$. It took me a while to understand, but we can summarize this technique as $B y = \sum_{k} b_k y_k$, where $b_k$ are the columns of $B$, and $y_k$ are the elements of the vector $y$[$^{[5]}$](https://math.stackexchange.com/questions/331826/expressing-a-matrix-as-an-expansion-of-its-eigenvalues). If everything is fine upto this point, we can continue with the rest of the proof.

Well done! We are now arriving at the "wiggle theorem", or the "perturbation theorem". Beware physicists! This is not the perturbation theory of physics, however you will see that it bears strong resemblance to the perturbation theory used in physics.

**Wiggle Theorem:** A symmetric (Hermitian) matrix can be approximated by symmetric (Hermitian) matrices with simple spectrum [$^{[3]}$](https://people.math.harvard.edu/~knill/teaching/math22b2019/handouts/lecture17.pdf).

**Proof**  
  
**Let** $A$ be an $n \times n$ symmetric (Hermitian) matrix. It has an eigenvalue $\lambda_1$ and an eigenvector $v_1$.

**Assume** $v_1$ is normalized.

**Define:**
$$
\begin{align}
A(t) &= A + t v_1 v_1^{\dagger} \\
&OR \nonumber \\
A(t) &= A + t |v_1\rangle \langle v_1| 
\end{align}
$$



By completeness relation, this $A(t)$ has the same eigenvector $v_1$ with a slighlty different eigenvalue $(\lambda_1 + t)$.
Remember that the eigenvalues of symmetric/Hermitian matrices were Real. Therefore this new $t$ should also be Real.  
  
The above equations show that a curve $A(t)$ can be defined in such a way that all the eigenvectors stay constant, and the eigenvalues are slighly perturbed.  
  
Still, we require that there should be $n$ distinct eigenvectors in $A$. How do we know that Hermitian matrices have this property? Check [$^{[6]}$](https://math.stackexchange.com/questions/227695/n-distinct-eigenvectors-for-an-n-times-n-hermitian-matrix). The proof involves Schur decomposition, and if you don't know that see the proof of Schur decomposition here [$^{[7]}$](https://www.statlect.com/matrix-algebra/Schur-decomposition). This is necessary to obtain an invertible $Q$ matrix where all the columns are linearly independent. What we aim to do is to diagonalize a matrix where it does not have $n$ distinct eigenvalues. The repeated eigenvalues can be slightly perturbed to obtain a new matrix with a simple spectrum $A(t)$. However, at the end of our calculations, we need to prove that this diagonalizations still exists in the limit $t \rightarrow 0$. Let's continue our discussion.  
  
Imagine that we have defined that matrix $A(t)$ with simple spectrum. This means we finally obtained $n$ distinct eigenvalues. Remember that the matrix $Q$ was constructed from the eigenvectors of $A$, thus also $A(t)$. The matrix $A$ was Hermitian, which means the eigenvectors for different eigenvalues are also orthogonal. If they are orthogonal, I can obtain my new $Q(t)$ from orthonormal eigenvectors of $A(t)$. But hey were the eigenvalues of $A$ originally, so I will call them simly $Q$. Thus:  

$$
A(t) = Q \Lambda(t) Q^{-1}
$$

Taking the limit $t \rightarrow 0$ we obtain eq. the eq. $\ref{diagonalization}$. Thus we proved all the Hermitian matrices are diagonalizable via use of unitary matrices, and all the symmetric matrices are diagonalizable by using orthogonal matrices.

  

<!-- $$
\begin{align}

\end{align}
$$
 -->


**Sources**
* Steen, L. A. “Highlights in the History of Spectral Theory.” The American Mathematical Monthly 80, no. 4 (1973): 359–81. https://doi.org/10.2307/2319079.

