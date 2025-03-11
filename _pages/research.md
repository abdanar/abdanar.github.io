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
It has already been shown that for state-space symmetric SISO systems, IRKA is a locally convergent fixed-point iteration to a local minimum of the underlying $$H_2$$ approximation problem. The question is whether a broader class of convergent systems can be identified that includes this condition. (i.e., symmetric system: $$H(s) = H^{T}(s)$$)

**Proposition**: Let $$(A, B, C)$$ be a stable state-space realization. A SISO system is state-space symmetric if and only if all there Gramians are equal.\
_Note:_ The Cross Gramian was first proposed for SISO systems and later extended to MIMO systems when the number of inputs and outputs are the same. Therefore, we assume that $$A\in\mathbb{R}^{n\times n}$$, $$B\in \mathbb{R}^{n\times m}$$, $$C\in \mathbb{R}^{p\times n}$$, where $$m=p$$. This proposition does not hold for MIMO systems.

**Proposition**: Every state-space symmetric system is a symmetric system.\
**proof**: A system is said to be state-space symmetric if there exists a minimal state-space realization $$(A, B, C)$$ satisfying $$A = A^{T}$$ and $$B^{T} = C$$. Then, we have

$$
H^{T}(s) = (C(sI - A)^{-1}B)^{T} = B^{T}(sI - A^{T})^{-1}C^{T} = C(sI - A)^{-1}B = H(s).
$$

_Note:_ The converse is not true in general.

The following problems remain open for me, and I will share detailed solutions as I find mathematical answers to them. You can think of them as conjectures awaiting either falsification or proof of their correctness.

- [ ] For state-space symmetric MIMO systems, IRKA is a locally convergent fixed-point iteration to a local minimum of the underlying $$H_2$$ approximation problem.\
      _Note_
- [ ] For state-space symmetric MIMO systems, IRKA is a locally convergent fixed-point iteration to a local minimum of the underlying $$H_2$$ approximation problem.
- [ ] Every state-space symmetric, stable MIMO system has a stable IRKA realization*.
- [ ] Every symmetric system has an IRKA realization* which is symmetric.

List of useful articles and books:

**Balanced Truncation**
- Sylvester, J. J. (1884). Sur l'équation en matrices $$px = xq$$. *Comptes Rendus de l'Académie des Sciences de Paris*, **99**, 67–71, 115–116.
- Gantmacher, F. R. (1959). *The Theory of Matrices* (Vol. 1). Chelsea Publishing Company.
- Kalman, R. E. (1960). On the general theory of control systems. *IFAC Proceedings Volumes*, 1(1), 491-502.
- Kalman, R. E., Falb, P. L., & Arbib, M. A. (1968). *Topics in Mathematical System Theory*. McGraw-Hill.
- Kalman, R. E. (1968). *Lectures on Controllability and Observability*.

**Interpolatory Model Order Reduction**
- Antoulas, A. C., Beattie, C. A., & Güğercin, S. (2020). *Interpolatory Methods for Model Reduction*. Society for Industrial and Applied Mathematics.



