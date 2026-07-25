---
title: "The Derivative"
collection: lessons
permalink: /lessons/derivatives/
chapter: "1. Foundations of Calculus"
chapter_order: 1
lesson_order: 1
excerpt: "Definitions, geometric interpretation, and standard differentiation rules."
---

## 1. Motivation

Many quantities in mathematical biology change continuously — population density, drug concentration, resistant fraction — and we frequently want to know not just *how much* a quantity has changed, but *how fast* it is changing at a given instant.

Consider a function $y = f(x)$. Over an interval from $x$ to $x + \Delta x$, the quantity changes by

$$
\Delta y = f(x + \Delta x) - f(x).
$$

The **average rate of change** over this interval is the ratio

$$
\frac{\Delta y}{\Delta x} = \frac{f(x + \Delta x) - f(x)}{\Delta x},
$$

which is exactly the slope of the straight line (the secant) joining the two points $(x, f(x))$ and $(x + \Delta x, f(x + \Delta x))$ on the curve.

<div class="figure-with-text">
  <img src="{{ site.baseurl }}/images/lessons/fig1.svg" alt="Diagram showing nested large and small Delta x secant triangles converging toward the tangent line">
  <div class="figure-explanation">
    <p>
      The <span style="color:#fe6100;">orange secant line</span> spans a wide interval, $\Delta x_{\text{large}}$ (marked in <span style="color:#648fff;">blue</span>), giving only a rough approximation to the rate of change at $x_0$. The <span style="color:#dc267f;">pink secant line</span>, centred within the same span, uses a much narrower $\Delta x_{\text{small}}$: its slope sits closer to the true instantaneous rate. In both cases, the corresponding rise is marked in <span style="color:#24a148;">green</span> as $\Delta y$.
    </p>
    <p>
      As the interval shrinks further, the <span style="color:#dc267f;">pink secant</span> converges toward the tangent line at $x_0$, and the ratio $\Delta y / \Delta x$ converges toward the derivative $f'(x_0)$ — the limiting process stated formally in Definition 1.1.
    </p>
  </div>
</div>

This average rate depends on the size of $\Delta x$ chosen — a wide interval can smooth over rapid local behaviour a narrower one would capture. To recover the *instantaneous* rate of change at the single point $x$, we shrink the interval, letting $\Delta x \to 0$. As this happens, the secant line rotates and settles into the **tangent line** at $x$, and the ratio $\Delta y / \Delta x$ settles into a single limiting value — the derivative:

$$
\frac{dy}{dx} = \lim_{\Delta x \to 0} \frac{\Delta y}{\Delta x}.
$$

This is the same object introduced formally in Definition 1.1 below, with $h$ used in place of $\Delta x$ — the notation $dy/dx$ (due to Leibniz) emphasises this limiting process explicitly, treating $dy$ and $dx$ as infinitesimal versions of $\Delta y$ and $\Delta x$.

## 2. Definition

<div class="definition-box">
  <span class="box-title">Definition 1.1 (Derivative)</span>
  Let $f: \mathbb{R} \to \mathbb{R}$. The derivative of $f$ at $x$ is

  $$
  \begin{equation}
  f'(x) = \lim_{h \to 0} \frac{f(x+h) - f(x)}{h}
  \label{eq:derivative-def}
  \end{equation}
  $$

  provided this limit exists. If it does, $f$ is said to be **differentiable** at $x$.
</div>

<div class="remark-box">
  <span class="box-title">Remark</span>
  Common notations for the derivative include $f'(x)$, $\dfrac{df}{dx}$, $\dfrac{dy}{dx}$ (if $y = f(x)$), and $\dot{f}$ (typically reserved for derivatives with respect to time).
</div>

## 3. Geometric interpretation

The quotient in \eqref{eq:derivative-def} is the slope of the **secant line** through $(x, f(x))$ and $(x+h, f(x+h))$. As $h \to 0$, the secant line converges to the **tangent line** at $x$, and $f'(x)$ is precisely that tangent's slope.

## 4. Basic differentiation rules

<div class="theorem-box">
  <span class="box-title">Theorem 1.2 (Linearity)</span>
  If $f$ and $g$ are differentiable and $a, b \in \mathbb{R}$,

  $$
  \begin{equation}
  \frac{d}{dx}\left[a f(x) + b g(x)\right] = a f'(x) + b g'(x)
  \label{eq:linearity}
  \end{equation}
  $$
</div>

<div class="theorem-box">
  <span class="box-title">Theorem 1.3 (Product Rule)</span>

  $$
  \begin{equation}
  \frac{d}{dx}\left[f(x)g(x)\right] = f'(x)g(x) + f(x)g'(x)
  \label{eq:product-rule}
  \end{equation}
  $$
</div>

<div class="theorem-box">
  <span class="box-title">Theorem 1.4 (Quotient Rule)</span>

  $$
  \begin{equation}
  \frac{d}{dx}\left[\frac{f(x)}{g(x)}\right] = \frac{f'(x)g(x) - f(x)g'(x)}{g(x)^2}, \quad g(x) \neq 0
  \label{eq:quotient-rule}
  \end{equation}
  $$
</div>

<div class="theorem-box">
  <span class="box-title">Theorem 1.5 (Chain Rule)</span>
  If $h(x) = f(g(x))$,

  $$
  \begin{equation}
  h'(x) = f'(g(x)) \, g'(x)
  \label{eq:chain-rule}
  \end{equation}
  $$
</div>

## 5. Standard derivatives

<div class="theorem-box">
  <span class="box-title">Theorem 1.6 (Power Rule)</span>
  For $f(x) = x^n$, $n \in \mathbb{R}$,

  $$
  \begin{equation}
  f'(x) = n x^{n-1}
  \label{eq:power-rule}
  \end{equation}
  $$
</div>

The following standard results follow from first principles or the rules above, and are used freely throughout subsequent lessons:

| $f(x)$ | $f'(x)$ |
|---|---|
| $c$ (constant) | $0$ |
| $x^n$ | $nx^{n-1}$ |
| $e^x$ | $e^x$ |
| $a^x$, $a > 0$ | $a^x \ln a$ |
| $\ln x$ | $\dfrac{1}{x}$ |
| $\sin x$ | $\cos x$ |
| $\cos x$ | $-\sin x$ |
| $\tan x$ | $\sec^2 x$ |
| $\sqrt{x}$ | $\dfrac{1}{2\sqrt{x}}$ |
| $\dfrac{1}{x}$ | $-\dfrac{1}{x^2}$ |

## 6. Worked examples

<div class="example-box">
  <span class="box-title">Example 1.7</span>
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

<div class="example-box">
  <span class="box-title">Example 1.8</span>
  Let $f(x) = x^2 \sin x$. By the product rule \eqref{eq:product-rule},

  $$
  f'(x) = 2x \sin x + x^2 \cos x
  $$

  <details class="dropdown-box">
    <summary>Show step-by-step application</summary>
    Identify $u(x) = x^2$, $v(x) = \sin x$, so $u'(x) = 2x$, $v'(x) = \cos x$. Substituting into \eqref{eq:product-rule} gives $f'(x) = u'v + uv' = 2x\sin x + x^2 \cos x$ directly.
  </details>
</div>

<div class="example-box">
  <span class="box-title">Example 1.9</span>
  Let $f(x) = \sin(x^2)$. By the chain rule \eqref{eq:chain-rule} with outer function $\sin(\cdot)$ and inner function $x^2$,

  $$
  f'(x) = \cos(x^2) \cdot 2x
  $$

  <details class="dropdown-box">
    <summary>Show step-by-step application</summary>
    Let $g(x) = x^2$ and $u = g(x)$, so $f(x) = \sin(u)$. Then $\dfrac{df}{du} = \cos(u)$ and $\dfrac{du}{dx} = 2x$. By \eqref{eq:chain-rule}, $f'(x) = \cos(u) \cdot 2x = \cos(x^2) \cdot 2x$.
  </details>
</div>

<div class="remark-box">
  <span class="box-title">Remark</span>
  All rules stated here extend naturally to compositions — e.g. combining the chain rule with the standard derivatives table lets you differentiate expressions like $e^{\sin x}$ or $\ln(x^2 + 1)$ without returning to first principles each time.
</div>
