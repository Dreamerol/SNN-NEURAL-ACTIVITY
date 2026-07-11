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

## Hodgkin–Huxley Model Parameters

### State Variables

| Symbol | Description                                           |
| ------ | ----------------------------------------------------- |
| $V$    | Membrane potential (mV)                               |
| $m$    | Sodium ($\mathrm{Na}^+$) activation gating variable   |
| $h$    | Sodium ($\mathrm{Na}^+$) inactivation gating variable |
| $n$    | Potassium ($\mathrm{K}^+$) activation gating variable |

### Electrical Parameters

| Symbol                  | Description                                        |
| ----------------------- | -------------------------------------------------- |
| $C_m$                   | Membrane capacitance ($\mu\mathrm{F/cm^2}$)        |
| $I_{\mathrm{ext}}$      | External applied current ($\mu\mathrm{A/cm^2}$)    |
| $\bar{g}_{\mathrm{Na}}$ | Maximum sodium conductance ($\mathrm{mS/cm^2}$)    |
| $\bar{g}_{\mathrm{K}}$  | Maximum potassium conductance ($\mathrm{mS/cm^2}$) |
| $g_{\mathrm{L}}$        | Leak conductance ($\mathrm{mS/cm^2}$)              |
| $E_{\mathrm{Na}}$       | Sodium reversal potential (mV)                     |
| $E_{\mathrm{K}}$        | Potassium reversal potential (mV)                  |
| $E_{\mathrm{L}}$        | Leak reversal potential (mV)                       |

### Gating Functions

The functions $\alpha_m(V)$, $\beta_m(V)$, $\alpha_h(V)$, $\beta_h(V)$, $\alpha_n(V)$, and $\beta_n(V)$ are voltage-dependent rate constants that determine how quickly the ion channels open and close.

* $\alpha_m(V)$ – sodium channel activation rate
* $\beta_m(V)$ – sodium channel deactivation rate
* $\alpha_h(V)$ – sodium channel recovery (de-inactivation) rate
* $\beta_h(V)$ – sodium channel inactivation rate
* $\alpha_n(V)$ – potassium channel activation rate
* $\beta_n(V)$ – potassium channel deactivation rate

---

## Izhikevich Model Parameters

### State Variables

| Symbol | Description                                               |
| ------ | --------------------------------------------------------- |
| $v$    | Membrane potential (mV)                                   |
| $u$    | Membrane recovery variable representing recovery currents |

### Parameters

| Symbol | Description                                                    |
| ------ | -------------------------------------------------------------- |
| $I$    | External input current                                         |
| $a$    | Time scale of the recovery variable                            |
| $b$    | Sensitivity of the recovery variable to the membrane potential |
| $c$    | Membrane potential reset value after a spike                   |
| $d$    | Recovery variable reset increment after a spike                |

Different combinations of the parameters $a$, $b$, $c$, and $d$ produce different neuronal firing patterns, such as regular spiking, fast spiking, intrinsically bursting, chattering, and low-threshold spiking neurons.


\beta_n(V)=0.125\exp\left(-\frac{V}{80}\right)
$$
