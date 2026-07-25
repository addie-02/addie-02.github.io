---
title: "Higher-Order Derivatives"
collection: lessons
permalink: /lessons/higher-order-derivatives/
chapter: "1. Foundations of Calculus"
chapter_order: 1
lesson_order: 2
excerpt: "Second and higher derivatives, notation, and the Leibniz rule."
---

## 1. Motivation

The derivative $f'(x)$ is itself a function of $x$, so nothing stops us differentiating it again. Physically, if $f(t)$ is position, $f'(t)$ is velocity, and differentiating once more gives acceleration — the rate of change *of* the rate of change. In mathematical biology, second derivatives distinguish accelerating growth from decelerating growth even when the first derivative is positive in both cases.

## 2. Definition

<div class="definition-box" markdown="1">
<span class="box-title">Definition 2.1 (nth derivative)</span>
Let $f$ be differentiable on an interval. If $f'$ is itself differentiable, its derivative is the **second derivative** of $f$,

$$
\begin{equation}
f''(x) = \frac{d}{dx}\left[f'(x)\right] = \lim_{h \to 0} \frac{f'(x+h) - f'(x)}{h}.
\label{eq:second-derivative}
\end{equation}
$$

More generally, the **$n$th derivative** $f^{(n)}(x)$ is obtained by differentiating $f$ a total of $n$ times, provided each intermediate derivative exists.
</div>

<div class="remark-box" markdown="1">
<span class="box-title">Remark</span>
Common notations for higher-order derivatives: $f''(x)$, $f'''(x)$, $f^{(n)}(x)$ for $n \geq 4$; equivalently $\dfrac{d^2y}{dx^2}, \dfrac{d^3y}{dx^3}, \dfrac{d^ny}{dx^n}$ in Leibniz notation, or $\ddot{f}$ for a second time-derivative.
</div>

## 3. Geometric and physical interpretation

<div class="theorem-box" markdown="1">
<span class="box-title">Interpretation</span>
$f'(x) > 0$ means $f$ is increasing; $f''(x) > 0$ means the *rate* of increase is itself increasing — the curve bends upward (**convex**). Conversely $f''(x) < 0$ indicates the curve bends downward (**concave**). Points where $f''(x) = 0$ and concavity switches sign are **inflection points**.
</div>

<div class="example-box" markdown="1">
<span class="box-title">Example 2.2</span>
Logistic growth $f(t) = \dfrac{K}{1+e^{-rt}}$ has $f''(t) > 0$ for small $t$ (accelerating growth) and $f''(t) < 0$ as $f(t) \to K$ (decelerating growth), with the sign change marking the inflection point at $f(t) = K/2$ — the fastest-growth moment.
</div>

## 4. Differentiating repeatedly

<div class="theorem-box" markdown="1">
<span class="box-title">Theorem 2.3 (nth derivative of a power)</span>

$$
\frac{d^n}{dx^n}\left[x^m\right] = \frac{m!}{(m-n)!}\,x^{m-n}, \quad n \leq m,
$$

and $\dfrac{d^n}{dx^n}\left[x^m\right] = 0$ for $n > m$ (any integer $m$).
</div>

<div class="theorem-box" markdown="1">
<span class="box-title">Theorem 2.4 (Leibniz Rule)</span>
For a product of two functions,

$$
\begin{equation}
\frac{d^n}{dx^n}\left[f(x)g(x)\right] = \sum_{k=0}^{n} \binom{n}{k} f^{(k)}(x)\, g^{(n-k)}(x).
\label{eq:leibniz}
\end{equation}
$$

This generalises the product rule (Theorem 1.3, the $n=1$ case) to arbitrarily many differentiations, weighting terms by binomial coefficients.

<details class="dropdown-box" markdown="1">
<summary>Check against the ordinary product rule</summary>
Setting $n=1$ in \eqref{eq:leibniz} gives $\binom{1}{0}f g' + \binom{1}{1}f'g = fg' + f'g$, recovering Theorem 1.3 exactly.
</details>
</div>

## 5. Periodicity under repeated differentiation

<div class="example-box" markdown="1">
<span class="box-title">Example 2.5</span>
Trigonometric functions cycle every four derivatives:

$$
\sin x \to \cos x \to -\sin x \to -\cos x \to \sin x \to \cdots
$$

so $\dfrac{d^n}{dx^n}[\sin x]$ depends only on $n \bmod 4$.

<details class="dropdown-box" markdown="1">
<summary>Worked case: 10th derivative of sin(x)</summary>
$10 \bmod 4 = 2$, matching the second entry in the cycle, so $\dfrac{d^{10}}{dx^{10}}[\sin x] = -\sin x$.
</details>
</div>

<div class="example-box" markdown="1">
<span class="box-title">Example 2.6</span>
For $f(x) = e^{kx}$, every derivative reproduces the original function up to a power of $k$:

$$
f^{(n)}(x) = k^n e^{kx}.
$$

<details class="dropdown-box" markdown="1">
<summary>Show by induction</summary>
Base case $n=1$: $f'(x) = ke^{kx}$, matching Theorem 1.7. Inductive step: if $f^{(n)}(x) = k^n e^{kx}$, differentiating once more (Theorem 1.7 again) gives $f^{(n+1)}(x) = k^n \cdot k\, e^{kx} = k^{n+1}e^{kx}$.
</details>
</div>

<div class="remark-box" markdown="1">
<span class="box-title">Remark</span>
Higher-order derivatives underpin Taylor expansions (Lesson 3) and appear directly in PDE models throughout mathematical biology — e.g. the diffusion term $\partial^2 u/\partial x^2$ in reaction-diffusion equations is a second spatial derivative.
</div>
