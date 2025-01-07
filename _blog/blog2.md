---
layout: post
title: Grönwall's inequalaity
date: 2024-01-7 11:28:00-0400
description: an algorithm for solving tridiagonal systems of equations
permalink: /blog/blog2/
tags: inequality
categories: diffeqn
related_posts: false
---

\begin{lemma}[Grönwall's lemma in differential form]
Let $$I$$ be an interval of the real line of one of the forms $$[a, \infty)$$, $$[a, b]$$, or $$[a, b)$$ with $$a < b$$, and let $$\beta \in C(I)$$ such that $$\beta(t) \geq 0$$ for all $$t \in I$$. If $$v \in C^1(I)$$ is a nonnegative function that satisfies the inequality
\begin{equation*}
  v'(t) \leq \beta(t) v(t), \quad \text{for all } t \in I,
\end{equation*}
then
\begin{equation*}
  v(t) \leq v(a) \exp\left( \int_a^t \beta(s) \, ds \right), \quad \text{for all } t \in I.
\end{equation*}
\end{lemma}
