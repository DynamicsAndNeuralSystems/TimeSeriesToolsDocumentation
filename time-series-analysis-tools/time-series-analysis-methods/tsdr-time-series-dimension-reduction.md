---
icon: waveform
coverY: 0
---

# TSDR: time-series dimension reduction

<figure><img src="../.gitbook/assets/tsdr_categories.png" alt=""><figcaption></figcaption></figure>

{% embed url="https://github.com/DynamicsAndNeuralSystems/tsdr" %}

Time-series dimension reduction (TSDR) methods are a class of algorithms for the dimension reduction of multivariate data that exploit temporal structure. In contrast to general dimension reduction (GDR) methods, the outputs of which are invariant to temporal permutation, TSDR methods are sensitive to temporal structure.

The figure above visually summarises the categories of TSDR methods that we defined in Owens & Fulcher (2025). The first five categories (a-e) consist of methods that extract time-series components based on different aspects of temporal structure, i.e., slowness, autocorrelation, predictability, determinism, and non-stationarity. The final two categories (f-g) consist of methods that share a common methodology, i.e., diffusion-based and latent variable methods.

The _tsdr_ package provides python implementations of TSDR methods from each of these seven categories. The methods are written in a simple, readable style to enable time-series analysts to better understand a subset of the TSDR methods discussed in the Owens & Fulcher (2025) review paper.

If you use this software, please read and cite this open-access article:

* Owens & Fulcher (2025) [Time-series dimension reduction: a comprehensive review and conceptual unification of algorithms](https://www.techrxiv.org/users/999518/articles/1362320-time-series-dimension-reduction-a-comprehensive-review-and-conceptual-unification-of-algorithms), _TechRxiv_.

