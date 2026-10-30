---
description: >-
  A feature-based information-theoretic method for detecting interpretable,
  long-timescale pairwise interactions from time series.
coverY: 0
---

# 🖥️ Feature-based mutual info

## Original Paper 📕

Nguyen et al., _Physical Review Research_ (2025). "A feature-based information-theoretic approach for detecting interpretable, long-timescale pairwise interactions from time series". [Link](https://link.aps.org/doi/10.1103/qnx2-yp4c).

<figure><img src="../.gitbook/assets/Screenshot 2024-05-27 at 1.07.43 pm (1).png" alt=""><figcaption><p>This figure illustrates our method for detecting cases in which a target process, Y , is influenced by a statistical property of a recent time window of a source process, X. We contrast it to conventional MI, estimated directly from the signal-space of the variables, which we denote as MIs. (a) MIs is computed based on the observed time-series values of process X and Y. (b) MIf iterates through time-series segments of length l of process X and reduces each window to a single real-valued summary statistic zt. MI is then computed between feature variable Zt and the target variable Yt+1. </p></figcaption></figure>

## Public code repository (R)

R code is available [in this GitHub repository](https://github.com/DynamicsAndNeuralSystems/feature-mediated-dependency-detection), which includes code for implementing our method and for reproducing all results in our paper

















