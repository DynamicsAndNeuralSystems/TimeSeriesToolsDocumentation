---
description: >-
  This web resource provides an overview of the time-series analysis software
  that our research group has developed.
cover: .gitbook/assets/Screenshot 2024-07-02 at 15.54.06.png
coverY: 233.85611940298506
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

# 👋 Time-series software developed in the Dynamics and Neural Systems Group

We are the [Dynamics and Neural Systems Group](https://dynamicsandneuralsystems.github.io/) (led by A/Prof Ben Fulcher) and part of Complex Systems research in the School of Physics at the University of Sydney.

We are detectives :detective: interested in finding patterns in time-series measured from complex time-varying  systems :mag:. As part of this process, we often develop algorithms and analysis techniques that could be useful to researchers or general analysts interested in applying them on their own data.

Our group has developed three main types of software:

* Software for implementing highly comparative time-series analysis, in which a large library of scientific methods are implemented and compared.
* Feature subsets are efficiently coded (and high-performing) subsets of time-series features derived from the full set of features in _hctsa_.
* New types of specific time-series analysis methods developed in the group.

## Highly Comparative Toolkits

Software for implementing highly comparative time-series analysis, in which a large library of scientific methods are implemented and compared.

<table data-view="cards"><thead><tr><th align="center"></th><th align="center"></th><th align="center"></th><th data-hidden data-card-cover data-type="image">Cover image</th><th data-hidden data-card-cover-dark data-type="image">Cover image (dark)</th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td align="center"><em><strong>hctsa</strong></em><br><em>(Matlab)</em><br>>7000 univariate time-series analysis features and an associated analytic pipeline.</td><td align="center"></td><td align="center"></td><td><a href=".gitbook/assets/hctsa_small_logo_lightmode.png">hctsa_small_logo_lightmode.png</a></td><td></td><td><a href="highly-comparative-toolkits/hctsa.md">hctsa.md</a></td></tr><tr><td align="center"><em><strong>pyspi</strong></em><br><em>(python)</em><br>(>140 statistics of pairwise interaction between pairs of time series).</td><td align="center"></td><td align="center"></td><td><a href=".gitbook/assets/pyspi_small_logo_lightmode.png">pyspi_small_logo_lightmode.png</a></td><td></td><td><a href="highly-comparative-toolkits/pyspi.md">pyspi.md</a></td></tr><tr><td align="center"><strong>theft</strong><br>(<em>R</em>)<br>An R implementation of feature-based time-series analysis using open-source feature sets.</td><td align="center"></td><td align="center"></td><td><a href=".gitbook/assets/logo (4).png">logo (4).png</a></td><td></td><td><a href="highly-comparative-toolkits/theft.md">theft.md</a></td></tr><tr><td align="center"><em><strong>py-hctsa</strong></em></td><td align="center"><em>(Python)</em></td><td align="center">A native python implementation of hctsa with over 4000 univariate time-series analysis features.</td><td data-object-fit="contain"><a href=".gitbook/assets/pyhctsa_logo.png">pyhctsa_logo.png</a></td><td data-object-fit="contain"><a href=".gitbook/assets/pyhctsa_logo_dark (1).png">pyhctsa_logo_dark (1).png</a></td><td><a href="https://github.com/DynamicsAndNeuralSystems/pyhctsa">https://github.com/DynamicsAndNeuralSystems/pyhctsa</a></td></tr><tr><td align="center"><a href="https://github.com/DynamicsAndNeuralSystems/sync_osc_MSTMs"><em><strong>sync_osc_MSTMs</strong></em></a></td><td align="center">(<em>Matlab</em> &#x26; <em>Python</em>)</td><td align="center">>130 multi-neuron spike train measures of synchrony, oscillations, phase relationships, and spiking intensity and variability</td><td><a href=".gitbook/assets/raster_icon-1.png">raster_icon-1.png</a></td><td></td><td></td></tr></tbody></table>

## Feature Subsets

Efficiently coded (and high-performing) subsets of time-series features derived from the full set of features in _hctsa._

<table data-view="cards"><thead><tr><th align="center"></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td align="center"><em><strong>catch22</strong></em><br><em>(C, Matlab, R, Python, Julia)</em><br>A reduced set of 22 high-performing (and minimally redundant) time-series features.</td><td><a href=".gitbook/assets/catch22_small_logo_lightmode.png">catch22_small_logo_lightmode.png</a></td><td><a href="feature-subsets/catch22.md">catch22.md</a></td></tr><tr><td align="center"><em><strong>catchamouse16</strong></em><br><em>(C, Matlab, python)</em><br>A reduced set of 16 high-performing (and minimally redundant) features for analyzing fMRI time series.</td><td><a href=".gitbook/assets/catchamouse_small_logo_lightmode.png">catchamouse_small_logo_lightmode.png</a></td><td><a href="feature-subsets/catchamouse16.md">catchamouse16.md</a></td></tr></tbody></table>

## Time-Series Analysis Methods

Time-series analysis methods developed we've developed.

<table data-view="cards"><thead><tr><th align="center"></th><th align="center"></th><th data-hidden data-card-cover data-type="image">Cover image</th><th data-hidden data-card-target data-type="content-ref"></th><th data-hidden data-card-cover-dark data-type="image">Cover image (dark)</th></tr></thead><tbody><tr><td align="center"><strong>Rescaled Auto-Density (RAD)</strong><br><em>(Matlab, python, Julia)</em><br>An efficient method to infer the distance to a critical point from noisy time series.</td><td align="center"></td><td><a href=".gitbook/assets/KeyImage_med_wide.png">KeyImage_med_wide.png</a></td><td><a href="time-series-analysis-methods/rad.md">rad.md</a></td><td></td></tr><tr><td align="center"><strong>Feature-based mutual information (MIf)</strong><br><em>(python)</em><br>A method to infer long-timescale, feature-mediated interactions between processes.</td><td align="center"></td><td><a href=".gitbook/assets/Screenshot 2024-05-27 at 1.13.16 pm (1).png">Screenshot 2024-05-27 at 1.13.16 pm (1).png</a></td><td><a href="time-series-analysis-methods/feature-based-mutual-info.md">feature-based-mutual-info.md</a></td><td></td></tr><tr><td align="center"><strong>MPSTime</strong></td><td align="center">A quantum-inspired method for estimation of the time-series joint probability distribution using matrix-product states (MPS).</td><td data-object-fit="contain"><a href=".gitbook/assets/text40096.png">text40096.png</a></td><td><a href="time-series-analysis-methods/mpstime.md">mpstime.md</a></td><td data-object-fit="contain"><a href=".gitbook/assets/text43355.png">text43355.png</a></td></tr><tr><td align="center"><strong>Time-series dimension reduction (TSDR)</strong><br><em>(python)</em><br>Python implementations of time-series dimension reduction methods from seven algorithm categories.</td><td align="center"></td><td data-object-fit="contain"><a href=".gitbook/assets/tsdr_logo.png">tsdr_logo.png</a></td><td><a href="time-series-analysis-methods/tsdr-time-series-dimension-reduction.md">tsdr-time-series-dimension-reduction.md</a></td><td data-object-fit="contain"><a href=".gitbook/assets/tsdr_logo_dark.png">tsdr_logo_dark.png</a></td></tr></tbody></table>



