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
In practice, stability is not typically an issue, but it is still possible to obtain an unstable reduced-order system. However, one can easily see that for a stable SISO linear dynamical system, the reduced system is also stable. If $$A$$ is negative definite (or Hurwitz), then

$$
y^{T}A_{r}y = y^{T}Q_{r}^{T}AQ_{r}y = (Q_{r}y)^{T}A(Q_{r}y) = x^{T}Ax < 0,
$$

where $$Q_{r}$$ is an orthonormal basis for the (left) modeling subspace $$\mathcal{V}_{r}$$ and has full column rank.

**Is it possible to derive a general convergence result for IRKA?**  
It has already been shown that for state-space symmetric SISO systems, IRKA is a locally convergent fixed-point iteration to a local minimum of the underlying $$H_2$$ approximation problem. The question is whether a broader class of convergent systems can be found, which includes this condition.(i.e., if the observability and reachability Gramians are equal, consider the case where $$A = A^T$$ and $$BB^T = C^T C$$.)



List of useful articles and books:

**Balanced Truncation**
- Sylvester, J. J. (1884). Sur l'équation en matrices $$px = xq$$. *Comptes Rendus de l'Académie des Sciences de Paris*, **99**, 67–71, 115–116.
- Gantmacher, F. R. (1959). *The Theory of Matrices* (Vol. 1). Chelsea Publishing Company.
- Kalman, R. E. (1960). On the general theory of control systems. *IFAC Proceedings Volumes*, 1(1), 491-502.
- Kalman, R. E., Falb, P. L., & Arbib, M. A. (1968). *Topics in Mathematical System Theory*. McGraw-Hill.
- Kalman, R. E. (1968). *Lectures on Controllability and Observability*.

**Interpolatory Model Order Reduction**
- Antoulas, A. C., Beattie, C. A., & Güğercin, S. (2020). *Interpolatory Methods for Model Reduction*. Society for Industrial and Applied Mathematics.



