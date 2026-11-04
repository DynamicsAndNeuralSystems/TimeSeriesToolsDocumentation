---
description: >-
  The Rescaled Auto-Density (RAD) is a noise-robust metric for inferring the
  distance to criticality (the DTC). It aims to perform well in settings where
  the noise level varies between time series.
cover: ../.gitbook/assets/Figure_5 (9).png
coverY: 0
layout:
  width: default
  cover:
    visible: true
    size: hero
    mask: none
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
  tags:
    visible: true
  actions:
    visible: true
  anchors:
    visible: true
---

# 😎 RAD

### 📕 Original Paper&#x20;

📙 B. Harris, L. Gollo, B.D. Fulcher. "Tracking the distance to criticality in systems with unknown noise", [_Physical Review X_ **14**: 031021 (2024)](https://doi.org/10.1103/PhysRevX.14.031021).

### ❓ What is RAD?

In the original paper, we use a data-driven approach to develop theory on how to infer the DTC in the variable-noise setting. This theory relies on two key time-series properties: i) the distribution of values; and ii) the scale of fast fluctuations. Combining these two properties, such as by curve-fitting the distribution and solving the Fokker--Planck equation, partials-out the noise strength to give a noise-robust estimate of the shape of the potential function (and hence the control parameter). RAD implements these key algorithmic steps in a simplified way, efficiently estimating the DTC from data using elementary time-series operations. In RAD, the two algorithmic elements are captured by standard deviations above and below the median value (measuring the distribution) and the standard deviation of lag-1 differences (measuring fast fluctuations). Our RAD feature is given by:

$$
f_\textrm{RAD} = \sigma(\Delta \mathbf{x}) \left[\frac{1}{\sigma(U)} - \frac{1}{\sigma(L)} \right]\,,
$$

where $$\mathbf{x}$$ is the input time series, $$\Delta$$is the lag-1 difference operator, $$\sigma(\cdot)$$ is the standard deviation, and:

$$
U = \{x_t: x_t \geq \tilde{x}\}\,,\\L = \{x_t: x_t < \tilde{x}\}\,,
$$

where $$\tilde{x}$$ is the median value of $$\mathbf{x}$$.

### 🏃 Running RAD in Matlab, Julia, and Python

Code for RAD in **Matlab**, **Julia**, and **Python** is collected in the [RAD GitHub repository](https://github.com/DynamicsAndNeuralSystems/RAD).
In all three languages the function is called as `RAD(x, tau = 1, doCentre = true)`.

RAD is also available through existing toolboxes in Python, Matlab, and Julia:

* **Python**: in [_pyhctsa_](https://github.com/DynamicsAndNeuralSystems/pyhctsa), as [`pyhctsa.operations.criticality.rad`](https://dynamicsandneuralsystems.github.io/pyhctsa/generated/pyhctsa.operations.criticality.rad.html) (pyhctsa is where the hctsa feature library is actively developed)
* **Matlab**: in [_hctsa_](https://github.com/benfulcher/hctsa) (as of `v1.08`), as the [`CR_RAD()`](https://github.com/benfulcher/hctsa/blob/main/Operations/CR_RAD.m) master function, and `CR_RAD_1`, `CR_RAD_2`, and `CR_RAD_tau` operations
* **Julia**: in the [`TimeseriesFeatures.jl`](https://github.com/brendanjohnharris/TimeseriesFeatures.jl) package (`StatsBase.jl` extension), as the `CR_RAD::Feature`

### ⚠️ Usage Guide

RAD is best suited to univariate, regularly-sampled time-series data. The sampling period should be constant between time series, and if the time series are excessively smooth or over-sampled then the `tau` parameter should be set to a value greater than 1 (a suitable `tau` can often be inferred by inspecting the autocorrelation function of a time series).

RAD also includes an optional centering step (`doCentre`, on by default), which centers the time series at its median and takes absolute values.
It should be enabled if the time series do not represent radial values (e.g., enable `doCentre` if the distribution is approximately symmetric or 'two-sided').

