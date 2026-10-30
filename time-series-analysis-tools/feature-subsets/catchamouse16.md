---
description: CAnonical Time-series CHaracteristics for Mouse fMRI
cover: ../.gitbook/assets/catchamouse_small_logo_lightmode (2).png
coverY: -4
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

# 🐭 catchaMouse16

The _catchaMouse16_ feature set provides a useful set of features to summarize the dynamics of fMRI time-series data, with implementations for Python, MATLAB, and C.

Details are in the following (open) journal publication

{% hint style="success" %}
Alam et al. ["Canonical time-series features for characterizing biologically informative dynamical patterns in fMRI",](https://doi.org/10.52294/001c.140433) _Aperture_ (2025).
{% endhint %}

### 🏖️ Overview

* A specific **subset of 16 time-series features** from the [_hctsa_](https://github.com/benfulcher/hctsa/) time-series feature library designed to distinguish changes in functional Magnetic Resonance Imaging (fMRI) time series taken from mice undergoing experimental manipulations of excitatory and inhibitory neural activity in their cortical circuits.
* It is a collection of features that are generated from a general pipeline (which can be accessed [here](https://github.com/DynamicsAndNeuralSystems/Catchamouse16_paper_code)) applied to mouse fMRI time-series data taken from mice. This represents a high-performing but minimally redundant data-driven subset of the full library of _hctsa_ features, that best discriminate biologically relevant manipulations (using the DREADD technique) from non-invasive fMRI time series.

### 📓 Reading more about the background to _catchaMouse16_

For information on the full set of over 7000 time-series features on which catchaMouse16 was derived, see the following (open) publications:

* B.D. Fulcher and N.S. Jones. [_hctsa_: A computational framework for automated time-series phenotyping using massive feature extraction](http://www.cell.com/cell-systems/fulltext/S2405-4712\(17\)30438-6). _Cell Systems_ **5**, 527 (2017).
* B.D. Fulcher, M.A. Little, N.S. Jones [Highly comparative time-series analysis: the empirical structure of time series and their methods](http://rsif.royalsocietypublishing.org/content/10/83/20130048.full). _J. Roy. Soc. Interface_ **10**, 83 (2013).

The pipeline to reproduce to create the _catchaMouse16_ feature set is an adaptation of the general pipeline from C.H. Lubba, S.S. Sethi, P. Knaute, S.R. Schultz, B.D. Fulcher, N.S. Jones. [_catch22_: CAnonical Time-series CHaracteristics](https://doi.org/10.1007/s10618-019-00647-x). _Data Mining and Knowledge Discovery_ (2019).

### ⌨️ Installation

For C, MATLAB, and Python, the catchaMouse16 [Github repository](https://github.com/DynamicsAndNeuralSystems/catchaMouse16/) contains source code for building native binaries that can be called from these languages. You will need to download the source code, install [gsl](https://www.gnu.org/software/gsl/) (unix only), then follow the instructions below to build the binaries for your language.

For Julia users, these binaries have been [pre-built](https://github.com/JuliaBinaryWrappers/catchaMouse16_jll.jl/) for all platforms. You can use them by installing the [CatchaMouse16.jl](https://github.com/brendanjohnharris/CatchaMouse16.jl) package.

{% tabs %}
{% tab title="C-Compiled code" %}
Compile by executing the makefile inside the `catchaMouse16/C` by running `make`.&#x20;

Compute all the time-series features for some time-series data contained in `<infile>.`

```
./run_feat <infile> <outfile>
```

If an `<outfile` is not provided then the output is sent to the stdout.
{% endtab %}

{% tab title="Python" %}
Access the efficient python implementation of feature-set by running the following code:

{% code title="Terminal - Setup" %}
```
python3 setup_P3.py build
python3 setup_P3.py install
```
{% endcode %}

You can then test the features with

```
python3 test_features.py
```



The module is also available for python2:

{% code title="Terminal - Setup" %}
```
python2 setup.py build
python2 setup.py install
```
{% endcode %}

You can then test the features with

```
python2 test_features.py
```

The features are then accessible through a module which can be imported. Namely `import catchaMouse16`provides access to the features.

{% code title="Example usage" %}
```
import catchaMouse16
import numpy as np
ts_data = np.rand(100,1)
print(catchaMouse16.SC_FluctAnal_2_dfa_50_2_logi_r2_se2(ts_data))
```
{% endcode %}
{% endtab %}

{% tab title="MATLAB" %}
Open MATLAB, navigate to `catchaMouse16/MATLAB/`, and run `mexAll`. This brings the catchaMouse16 features into the namespace.

<pre data-title="Example usage"><code><strong>ts_data = randn(100,1) % column vector
</strong>catchaMouse16_all(ts_data)
</code></pre>

Individual features can be accessed as `catchaMouse16_{feature}`.
{% endtab %}

{% tab title="Julia" %}
Installation:

```
using Pkg
Pkg.add("CatchaMouse16")
```

Usage:

```
using CatchaMouse16
X = randn(1000, 10) # an Array{Float64, 2} with 10 time series
f = catchaMouse16[:AC_nl_035](X) # a 1×10 Matrix{Float64} (for a single feature)
F = catchaMouse16(X) # a 16×10 FeatureMatrix{Float64} (for 16 features)
```
{% endtab %}
{% endtabs %}

### ℹ Feature Descriptions

**Note**: All _catchaMouse16_ features are statistical properties of the _**z**_**-scored** time series - they aim to focus on the properties of the time-ordering of the data and are insensitive to the raw values in the time series.

The table below follows the same cypher as in [the catchaMouse16 paper](https://doi.org/10.52294/001c.140433) with the _hctsa_ name and an interpretable name referred to throughout the paper with corresponding descriptions.<br>

<table data-full-width="true"><thead><tr><th>Interpretable name</th><th>Feature name</th><th>Description</th><th data-hidden>#</th><th data-hidden>Category</th></tr></thead><tbody><tr><td><code>nonlin_autocorr_035</code></td><td><code>AC_nl_035</code></td><td><span class="math">\langle x_t^2 \,x_{t-3}\, x_{t-6} \rangle_t</span></td><td>1</td><td></td></tr><tr><td><code>nonlin_autocorr_036</code></td><td><code>AC_nl_036</code></td><td><span class="math">\langle x_t^2\, x_{t-3}\, x_{t-5}\rangle_t</span></td><td></td><td></td></tr><tr><td><code>nonlin_autocorr_112</code></td><td><code>AC_nl_112</code></td><td><span class="math">\langle x_t\, x_{t-1}^2\, x_{t-2} \rangle_t</span></td><td></td><td></td></tr><tr><td><code>ami3_10bin</code></td><td><code>CO_HistogramAMI_even_10bin_ami3</code></td><td>Automutual information at lag 3 using a 10-bin histogram estimation method</td><td></td><td></td></tr><tr><td><code>ami3_2bin</code></td><td><code>CO_HistogramAMI_even_2bin_ami3</code></td><td>Automutual information at lag 3 using a 2-bin histogram estimation method</td><td></td><td></td></tr><tr><td><code>increment_ami8</code></td><td><code>IN_AutoMutualInfoStats_diff_20_gaussian_ami8</code></td><td>Mutual information at time lag 8 using Gaussian estimator</td><td></td><td></td></tr><tr><td><code>dfa_longscale_fit</code></td><td><code>SC_FluctAnal_2_dfa_50_2_logi_r2_se2</code></td><td>Timescale–fluctuation curve using DFA</td><td></td><td></td></tr><tr><td><code>noise_titration</code></td><td><code>CO_AddNoise_1_even_10_ami_at_10</code></td><td>Automutual information at lag 1 after adding white noise at a SNR of 1</td><td></td><td></td></tr><tr><td><code>prediction_scale</code></td><td><code>FC_LoopLocalSimple_mean_stderr_chn</code></td><td><p>Change in </p><p>prediction error from a mean forecaster using prior windows of data</p></td><td></td><td></td></tr><tr><td><code>floating_circle</code></td><td><code>CO_TranslateShape_circle_35_pts_std</code></td><td>Variability of time-series points inside a circle translated across the time domain</td><td></td><td></td></tr><tr><td><code>walker_crossings</code></td><td><code>PH_Walker_momentum_5_w_momentumzcross</code></td><td>Statistics of a simulated mechanical particle driven by the time series</td><td></td><td></td></tr><tr><td><code>walker_diff</code></td><td><code>PH_Walker_biasprop_05_01_sw_meanabsdiff</code></td><td>Statistics of a simulated mechanical particle driven by the time series</td><td></td><td></td></tr><tr><td><code>stationarity_min</code></td><td><code>SY_DriftingMean50_min</code></td><td>Minimum mean across 50 segments divided by mean variance in segments</td><td></td><td></td></tr><tr><td><code>stationarity_floating_circle</code></td><td><code>CO_TranslateShape_circle_35_pts_statav4_m</code></td><td>StatAv of the statistics of local time-series shapes</td><td></td><td></td></tr><tr><td><code>outlier_corr</code></td><td><code>DN_RemovePoints_absclose_05_ac2rat</code></td><td>Change in lag-2 autocorrelation from removing 50% of the time-series values closest to the mean</td><td></td><td></td></tr><tr><td><code>outlier_asymmetry</code></td><td><code>ST_LocalExtrema_n100_diffmaxabsmin</code></td><td>Asymmetry in extreme local events</td><td></td><td></td></tr></tbody></table>



