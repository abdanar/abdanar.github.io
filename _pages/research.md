---
layout: page
permalink: /research/
title: research
nav: true
nav_order: 1
---

As an interested student in the IRKA (Iterative Rational Krylov Algorithm) method, I have several questions that I have not mathematically proven. If you know the answer to any of them, please contact me.

**How to choose the initial shift selection?**  
One may choose initial shifts randomly, distributed within a region containing the mirror image of the numerical range of matrix $$A$$, as the eigenvalues of the reduced matrix $$A_r$$ might approximate the eigenvalues of $$A$$. However, in practice, random initial shifts tend to perform better than this, and there might be a better approach for selecting the initial points.

**What conditions exist to ensure the resulting reduced system is stable?**  
In practice, stability is not typically an issue, but it is still possible to obtain an unstable reduced-order system. However, one can easily see that for a stable, state-space symmetric SISO linear dynamical system, the reduced system is also stable. If $$A$$ is negative definite (or Hurwitz), then

$$
y^{T}A_{r}y = y^{T}Q_{r}^{T}AQ_{r}y = (Q_{r}y)^{T}A(Q_{r}y) = x^{T}Ax < 0,
$$

where $$Q_{r}$$ is an orthonormal basis for the (left) modeling subspace $$\mathcal{V}_{r}$$ and has full column rank.

**Is it possible to derive a general convergence result for IRKA?**  
It has already been shown that for state-space symmetric SISO systems, IRKA is a locally convergent fixed-point iteration to a local minimum of the underlying $$H_2$$ approximation problem. The question is whether a broader class of convergent systems can be identified that includes this condition. (i.e., symmetric system: $$H(s) = H^{T}(s)$$)

**Theorem**: For any stable state-space symmetric realization, all three Gramians are equal.\
**proof**: If $$B^{T} = C$$, then $$BC = BB^{T} = C^{T}C$$. Combining this observation with $$A$$ being symmetric, it follows from the definitions of the Gramians that all three Gramians are equal.

_Note:_ One should keep the following in mind:
- The Cross Gramian was first proposed for SISO systems and later extended to MIMO systems when the number of inputs and outputs are the same. Therefore, we assume that $$A\in\mathbb{R}^{n\times n}$$, $$B\in \mathbb{R}^{n\times m}$$, $$C\in \mathbb{R}^{p\times n}$$, where $$m=p$$.
- The converse of the statement does not hold for both SISO and MIMO systems.

**Theorem**: Every state-space symmetric system is a symmetric system.\
**proof**: A system is said to be state-space symmetric if there exists a minimal state-space realization $$(A, B, C)$$ satisfying $$A = A^{T}$$ and $$B^{T} = C$$. Then, we have

$$
H^{T}(s) = (C(sI - A)^{-1}B)^{T} = B^{T}(sI - A^{T})^{-1}C^{T} = C(sI - A)^{-1}B = H(s).
$$

_Note:_ The converse is not true in general. Thus, one can conclude that symmetry is an inherent property of the system, independent of its state-space realizations.

**Proposition**: Let $$M$$ be an $$n\times n$$ complex diagonalizable matrix. Then, $$M$$ has $$n$$ distinct eigenvalues if and only if there exists a vector $$v\in \mathbb{C}^n$$ such that $$v,Mv, ...,M^{n−1}v$$ are linearly independent. (see an article titled _A theorem on the number of distinct eigenvalues_ by Rachid Marsli)


There is an important question I have about the IRKA for the SISO case. In the article titled _Convergence of the Iterative Rational Krylov Algorithm_ by Garret Flagg, Christopher Beattie, and Serkan Gugercin, on page 3 they provide a brief sketch (as stated in the paper) of the Iterative Rational Krylov Algorithm for the SISO case. In the interpolation point update process — an iterative correction of the interpolation points — the new points are chosen as the eigenvalues of the reduced matrix $$A_r$$. However, a good question here is: how do you know that the eigenvalues of $$A_r$$ are distinct? Note that this is a general question, not specific to state-space symmetric systems. It might be straightforward to prove for the general case, but I have not yet come up with a mathematical proof. One might easily comment that the initial interpolation points are distinct, and therefore the eigenvalues of $$A_r$$ would be distinct. However, proving this is not straightforward, at least for me, since the eigenvectors are unpredictable. But there is good news! For state-space symmetric systems, we can mathematically show that the eigenvalues of the reduced matrix $$A_r$$ are distinct. This result follows from the symmetry of the matrix $$A$$. If $$A$$ is symmetric, then $$A_r$$ is symmetric, which implies that it is diagonalizable. If one uses the above proposition, it will show that $$A_r$$ has distinct eigenvalues. One might made statement here is that one may drop the condition $$B^{T} = C$$ and follows the same logic to get the result. However, $$A_r$$ is not symmetric anymore, and showing diagonalizablity is not an easier job.


The following problems remain open for me, and I will share detailed solutions as I find mathematical answers to them. You can think of them as conjectures awaiting either falsification or proof of their correctness.

- [ ] For state-space symmetric MIMO systems, IRKA is a locally convergent fixed-point iteration to a local minimum of the underlying $$H_2$$ approximation problem.\
      _Note_: Establish the connection between a ZIP system and a symmetric MIMO system
- [ ] There is always a stable IRKA realization* for a stable linear dynamical system (a proof for the state-space symmetric SISO case is provided above).
- [ ] Every state-space symmetric, stable MIMO system has a stable IRKA realization.
- [ ] Every symmetric system has a symmetric IRKA realization.

*a realization (A, B, C) obtained from IRKA

List of useful articles and books:

**Balanced Truncation**
- Sylvester, J. J. (1884). Sur l'équation en matrices $$px = xq$$. *Comptes Rendus de l'Académie des Sciences de Paris*, **99**, 67–71, 115–116.
- Gantmacher, F. R. (1959). *The Theory of Matrices* (Vol. 1). Chelsea Publishing Company.
- Kalman, R. E. (1960). On the general theory of control systems. *IFAC Proceedings Volumes*, 1(1), 491-502.
- Kalman, R. E., Falb, P. L., & Arbib, M. A. (1968). *Topics in Mathematical System Theory*. McGraw-Hill.
- Kalman, R. E. (1968). *Lectures on Controllability and Observability*.

**Interpolatory Model Order Reduction**
- Antoulas, A. C., Beattie, C. A., & Güğercin, S. (2020). *Interpolatory Methods for Model Reduction*. Society for Industrial and Applied Mathematics.



