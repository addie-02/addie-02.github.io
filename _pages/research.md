---
title: "Research"
layout: archive
permalink: /research/
---

## Projects

<div class="project-entry">
  <h3>Bee Foraging Agent-Based Model</h3>
  <img src="{{ site.baseurl }}/images/projects/bee-abm-plot.png" alt="Bee ABM simulation output" style="max-width:100%; border-radius: 8px;">
  <p>A lattice-based agent-based model of bee foraging behaviour, incorporating flower pollination dynamics, waggle-dance-style recruitment, and Q-learning for adaptive foraging strategy. Implemented in Python.</p>
  <p><a href="https://github.com/addie-02/A-Bee_M" target="_blank">View repository →</a></p>
</div>

<div class="project-entry">
  <h3>National Grid: Function-on-Function Electricity Demand Forecasting</h3>
  <img src="{{ site.baseurl }}/images/projects/fda-demand-plot.png" alt="FDA electricity demand forecast" style="max-width:100%; border-radius: 8px;">
  <p>SAMBa ITT24 project modelling UK electricity demand via function-on-function regression (<code>pffr()</code>, R), with functional covariates for lagged demand, temperature, wind speed, and activity profiles across five UK cities. Post-modelling analysis included FPCA and covariance surface visualisation.</p>
  <p><a href="https://github.com/addie-02/ITT24-FDA-NGED" target="_blank">View repository →</a></p>
</div>

<div class="project-entry">
  <h3>Adaptive Therapy: Resistance Formation Modelling</h3>
  <img src="{{ site.baseurl }}/images/projects/at-model-plot.png" alt="Adaptive therapy model dynamics" style="max-width:100%; border-radius: 8px;">
  <p>Extension of a Lotka-Volterra competition model (Gallagher et al., 2025) with a drug-concentration-dependent resistance formation function λ(D; c), PK drug decay, and bactericidal death rates, comparing constant, adaptive, and threshold dosing regimes.</p>
  <p><a href="https://github.com/addie-02/" target="_blank">View repository →</a></p>
</div>

---

## Papers

{% for pub in site.publications reversed %}
  <div class="paper-entry">
    <h3>{{ pub.title }}</h3>
    <p><em>{{ pub.venue }}</em>, {{ pub.date | date: "%Y" }}</p>
    <p>{{ pub.excerpt }}</p>
    <p><a href="{{ pub.paperurl }}" target="_blank">Full paper →</a></p>
  </div>
{% endfor %}

{% if site.publications.size == 0 %}
  <p><em>No papers published yet — check back soon!</em></p>
{% endif %}
