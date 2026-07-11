# Introduction

This repository explores computational neuroscience through the implementation and analysis of biologically inspired neuron models and Spiking Neural Networks (SNNs). The project focuses on simulating neuronal dynamics, processing neural action potentials, and studying how information is represented and transmitted through spikes.

The repository includes implementations of the **Hodgkin–Huxley (HH)** and **Izhikevich** neuron models to simulate and compare the behavior of different neuronal types. In addition, it implements spike-based encoding and decoding techniques, enabling the transformation of continuous signals into spike trains and the reconstruction of information from neural activity.

The project also investigates different neuron firing patterns, analyzes the characteristics of generated action potentials, and demonstrates how SNNs can process spike-based information. Together, these components provide a foundation for studying neural computation, biologically plausible learning, and neural signal processing.

## Hodgkin–Huxley Model

The membrane potential is governed by

$$
C_m \frac{dV}{dt} = I_{\mathrm{ext}} - \bar{g}_{\mathrm{Na}} m^3 h (V - E_{\mathrm{Na}}) - \bar{g}_{\mathrm{K}} n^4 (V - E_{\mathrm{K}}) - g_{\mathrm{L}} (V - E_{\mathrm{L}})
$$

The gating variables evolve according to

$$
\frac{dm}{dt} = \alpha_m(V)(1-m) - \beta_m(V)m
$$

$$
\frac{dh}{dt} = \alpha_h(V)(1-h) - \beta_h(V)h
$$

$$
\frac{dn}{dt} = \alpha_n(V)(1-n) - \beta_n(V)n
$$

where

$$
\alpha_m(V)=\frac{0.1(25-V)}{\exp\left(\frac{25-V}{10}\right)-1}
$$

$$
\beta_m(V)=4\exp\left(-\frac{V}{18}\right)
$$

$$
\alpha_h(V)=0.07\exp\left(-\frac{V}{20}\right)
$$

$$
\beta_h(V)=\frac{1}{\exp\left(\frac{30-V}{10}\right)+1}
$$

$$
\alpha_n(V)=\frac{0.01(10-V)}{\exp\left(\frac{10-V}{10}\right)-1}
$$

$$
\beta_n(V)=0.125\exp\left(-\frac{V}{80}\right)
$$
