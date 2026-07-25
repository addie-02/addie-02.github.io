---
permalink: /teaching/lessons/derivatives/
title: "Lesson 1: The Derivative"
author_profile: true
---

## 1. Motivation

We want to formalise the notion of an *instantaneous rate of change* — how a function's output changes as its input changes at a single point, rather than over an interval.

<div class="definition-box">
  <span class="box-title">Definition 1.1 (Derivative)</span>
  Let $f: \mathbb{R} \to \mathbb{R}$. The derivative of $f$ at $x$ is

  $$
  \begin{equation}
  f'(x) = \lim_{h \to 0} \frac{f(x+h) - f(x)}{h}
  \label{eq:derivative-def}
  \end{equation}
  $$

  provided this limit exists.
</div>

## 2. Geometric interpretation

The quotient in \eqref{eq:derivative-def} is the slope of the **secant line** through $(x, f(x))$ and $(x+h, f(x+h))$. As $h \to 0$, the secant line converges to the **tangent line** at $x$.

## 3. Basic differentiation rules

<div class="theorem-box">
  <span class="box-title">Theorem 1.2 (Power Rule)</span>
  For $f(x) = x^n$, $n \in \mathbb{R}$,

  $$
  \begin{equation}
  f'(x) = n x^{n-1}
  \label{eq:power-rule}
  \end{equation}
  $$
</div>

<div class="example-box">
  <span class="box-title">Example 1.3</span>
  Let $f(x) = x^3$. By \eqref{eq:power-rule}, $f'(x) = 3x^2$.

  <details class="dropdown-box">
    <summary>Show derivation from first principles</summary>

    $$
    f'(x) = \lim_{h \to 0} \frac{(x+h)^3 - x^3}{h}
    = \lim_{h \to 0} \frac{3x^2 h + 3xh^2 + h^3}{h}
    = \lim_{h \to 0} \left(3x^2 + 3xh + h^2\right) = 3x^2
    $$
  </details>
</div>

<div class="remark-box">
  <span class="box-title">Remark</span>
  The power rule extends to negative and fractional exponents — e.g. $f(x) = x^{-1} \Rightarrow f'(x) = -x^{-2}$, and $f(x) = \sqrt{x} = x^{1/2} \Rightarrow f'(x) = \tfrac{1}{2}x^{-1/2}$.
</div>
