---
description: >-
  A quantum inspired method for estimating the time-series joint distribution
  using matrix-product states (MPS).
icon: atom-simple
cover:
  light: ../.gitbook/assets/lightmode_logo.png
  dark: ../.gitbook/assets/darkmode_logo.png
coverY: -1501.9180904522614
---

# MPSTime

## Original Paper :green\_book:

J.B. Moore, H.P. Stackhouse, B.D. Fulcher, S. Mahmoodian. "Using matrix-product states for time-series machine learning", [_Physical Review Research 7: 043010 (2025)_](https://link.aps.org/doi/10.1103/61h8-8qr5)_._

<figure><img src="../.gitbook/assets/path1 (1).png" alt=""><figcaption><p>MPSTime, a framework for time-series machine learning with MPSs. (a) Encoding: Each real-valued time series amplitude 𝑥<sub>𝑡</sub> is encoded in a 𝑑-dimensional vector 𝜙<sub>𝑡</sub> by projecting its value onto a truncated orthonormal basis with 𝑑 basis functions. An entire time series (of length 𝑇 samples) is then encoded as a set of 𝑇 𝜙<sub>𝑡</sub> vectors, which we represent as a product state embedded in a 𝑑<sup>𝑇</sup>-dimensional Hilbert space. (b) MPS training: Using observed time series from a dataset, a generally entangled MPS—depicted here using Penrose graphical notation—with maximum bond dimension 𝜒<sub>max</sub> is trained with a DMRG-inspired sweeping optimization algorithm to approximate the joint distribution of the training data. Two copies of the trained MPS (one conjugate-transposed, denoted by the dagger †) with open physical indices encodes the learned distribution, allowing us to sample from and do inference with complex high-dimensional time-series distributions. In this work, we introduce MPS-based learning algorithms, which we collectively refer to as MPSTime, for two important time-series ML problems: (c) imputation (inferring unmeasured values of a time series) and (d) classification (inferring a time-series class). (c) Generative time-series modeling: We use conditional sampling to perform imputation of missing datapoints. Known points of a single time-series instance (black lines) project the MPS into a subspace, which is then used to find the unknown datapoints (red line). The same method can be used to tackle some forecasting problems if the missing points are future values. (d) MPS for classification: Multiple labeled classes of time series are used to train MPSs. Taking the overlap of unlabeled time-series data (encoded as a product state) with each MPS determines its class.</p></figcaption></figure>

## Public code repository (Julia)

Julia code is available [in this GitHub repository](https://github.com/hugopstackhouse/MPSTime.jl), which includes code for implementing our method and for reproducing all results in our paper:

{% embed url="https://github.com/hugopstackhouse/MPSTime.jl" %}



