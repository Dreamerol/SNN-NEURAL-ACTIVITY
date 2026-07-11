<div align="center">

# 🧠 NEUROSCONCE SNN





<img src="https://raw.githubusercontent.com/Dreamerol/Dreamerol/main/brainone.jpg" width="100%"/>

</div>



<br>



<p align="center">

<img src="https://img.shields.io/badge/SNN-red?style=for-the-badge">
<img src="https://img.shields.io/badge/AI-purple?style=for-the-badge">
<img src="https://img.shields.io/badge/Neuroscience-green?style=for-the-badge">
<img src="https://img.shields.io/badge/HH-orange?style=for-the-badge">
<img src="https://img.shields.io/badge/Izhikevich-blue?style=for-the-badge">
<img src="https://img.shields.io/badge/ActionPotential-yellow?style=for-the-badge">
<img src="https://img.shields.io/badge/Neuromorphic-brightgreen?style=for-the-badge">
<img src="https://img.shields.io/badge/EulerMethod-red?style=for-the-badge">
<img src="https://img.shields.io/badge/DifferentialSystems-purple?style=for-the-badge">
<img src="https://img.shields.io/badge/NeuronDynamics-green?style=for-the-badge">
<img src="https://img.shields.io/badge/SpikeEncoding-orange?style=for-the-badge">
<img src="https://img.shields.io/badge/SpikeDecoding-blue?style=for-the-badge">
<img src="https://img.shields.io/badge/NeuralCoding-yellow?style=for-the-badge">
<img src="https://img.shields.io/badge/BrainSimulation-brightgreen?style=for-the-badge">

</p>


</div>



<br>



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

## Results and Observations

The performance of the different Izhikevich neuron types was evaluated using the Mean Squared Error (MSE) loss:


| Neuron Type                 | MSE    |
| --------------------------- | ------ |
| Regular Spiking (RS)        | 1.8344 |
| Intrinsically Bursting (IB) | 1.8486 |
| Chattering (CH)             | 1.8198 |
| Low Frequency + Chattering  | 1.7633 |


The results show that the **Chattering neuron provides the lowest error among the standard neuron types**, achieving better reconstruction accuracy compared to Regular Spiking and Intrinsically Bursting neurons. The combination of **Low Frequency and Chattering behavior achieves the lowest MSE**, indicating that this firing pattern provides the most suitable spike representation for the given task.

A possible explanation is that chattering neurons generate groups of closely spaced spikes, allowing them to represent detailed temporal information in the input signal. However, using an excessively high firing frequency can negatively affect performance because it may introduce redundant spikes, increase noise in the spike representation, and make decoding less accurate. A very high spike rate does not necessarily contain more useful information and can reduce the efficiency of the encoding process.

The Low Frequency + Chattering configuration provides a balance between temporal precision and spike efficiency. The lower firing rate prevents unnecessary spike generation, while the chattering behavior preserves important information through burst-based communication. This balance leads to a more accurate reconstruction of the original function and the lowest MSE value.

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


## Izhikevich Model

The Izhikevich neuron model combines biological plausibility with computational efficiency.

### Membrane Potential

$$
\frac{dv}{dt} = 0.04v^2 + 5v + 140 - u + I
$$

### Recovery Variable

$$
\frac{du}{dt} = a(bv-u)
$$

### Spike Reset

When the membrane potential reaches the spike threshold,

$$
v \ge 30\ \mathrm{mV},
$$

the neuron is reset according to

$$
v \leftarrow c,\qquad u \leftarrow u + d
$$


<br>


<p align="center">

<img src="https://img.shields.io/badge/SNN-red?style=for-the-badge">
<img src="https://img.shields.io/badge/AI-purple?style=for-the-badge">
<img src="https://img.shields.io/badge/Neuroscience-green?style=for-the-badge">
<img src="https://img.shields.io/badge/HH-orange?style=for-the-badge">
<img src="https://img.shields.io/badge/Izhikevich-blue?style=for-the-badge">
<img src="https://img.shields.io/badge/ActionPotential-yellow?style=for-the-badge">
<img src="https://img.shields.io/badge/Neuromorphic-brightgreen?style=for-the-badge">
<img src="https://img.shields.io/badge/EulerMethod-red?style=for-the-badge">
<img src="https://img.shields.io/badge/DifferentialSystems-purple?style=for-the-badge">
<img src="https://img.shields.io/badge/NeuronDynamics-green?style=for-the-badge">
<img src="https://img.shields.io/badge/SpikeEncoding-orange?style=for-the-badge">
<img src="https://img.shields.io/badge/SpikeDecoding-blue?style=for-the-badge">
<img src="https://img.shields.io/badge/NeuralCoding-yellow?style=for-the-badge">
<img src="https://img.shields.io/badge/BrainSimulation-brightgreen?style=for-the-badge">

</p>


</div>



<br>


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

$$

The Hodgkin–Huxley (HH) model is more biologically accurate because it simulates ion channels and membrane dynamics, but it is slower and more computationally expensive due to its complexity. The Izhikevich model simplifies neuronal behavior, making it much faster and suitable for large-scale Spiking Neural Networks while still reproducing different firing patterns.


<p align="center">

<img src="https://img.shields.io/badge/SNN-red?style=for-the-badge">
<img src="https://img.shields.io/badge/AI-purple?style=for-the-badge">
<img src="https://img.shields.io/badge/Neuroscience-green?style=for-the-badge">
<img src="https://img.shields.io/badge/HH-orange?style=for-the-badge">
<img src="https://img.shields.io/badge/Izhikevich-blue?style=for-the-badge">
<img src="https://img.shields.io/badge/ActionPotential-yellow?style=for-the-badge">
<img src="https://img.shields.io/badge/Neuromorphic-brightgreen?style=for-the-badge">
<img src="https://img.shields.io/badge/EulerMethod-red?style=for-the-badge">
<img src="https://img.shields.io/badge/DifferentialSystems-purple?style=for-the-badge">
<img src="https://img.shields.io/badge/NeuronDynamics-green?style=for-the-badge">
<img src="https://img.shields.io/badge/SpikeEncoding-orange?style=for-the-badge">
<img src="https://img.shields.io/badge/SpikeDecoding-blue?style=for-the-badge">
<img src="https://img.shields.io/badge/NeuralCoding-yellow?style=for-the-badge">
<img src="https://img.shields.io/badge/BrainSimulation-brightgreen?style=for-the-badge">

</p>

## Action Potential

An action potential is a rapid change in the membrane potential of a neuron that allows it to transmit information through electrical signals. It is generated when the membrane potential reaches a threshold, causing voltage-gated ion channels to open and produce a sequence of voltage changes.

* **Resting potential:** The neuron is normally around **-70 mV**, maintained by ion gradients and membrane pumps. The inside of the neuron is more negative compared to the outside.

* **Depolarization:** When a stimulus reaches the threshold, **sodium ($Na^+$) channels open**, allowing sodium ions to enter the cell. This makes the membrane potential more positive and causes the rising phase of the action potential.

* **Peak:** The membrane potential reaches its maximum value (around **+30 mV**). At this point, sodium channels become inactive and potassium ($K^+$) channels begin to open.

* **Repolarization:** Potassium ions leave the cell through open potassium channels, causing the membrane potential to become negative again.

* **Hyperpolarization:** Potassium channels remain open slightly longer than needed, causing the membrane potential to drop below the resting potential (more negative than -70 mV). This period reduces the probability of generating another action potential.

* **Return to resting potential:** Ion channels return to their normal state, and the membrane potential stabilizes back to the resting level.

This process allows neurons to encode and transmit information using the timing and frequency of spikes.

## Izhikevich Neuron Types

* **Regular Spiking (RS):** Produces single spikes at regular intervals. This type of neuron shows spike-frequency adaptation, where the firing rate decreases over time during continuous stimulation.

* **Intrinsically Bursting (IB):** Generates bursts of multiple spikes at the beginning of stimulation, followed by slower firing activity. This pattern is common in neurons involved in signal integration.

* **Chattering (CH):** Produces high-frequency bursts of closely spaced spikes. These neurons can generate rhythmic firing patterns and are important for precise temporal coding.

## Izhikevich Neuron Parameters

The firing behavior of Izhikevich neurons is controlled by the parameters $a$, $b$, $c$, and $d$.


| Neuron Type                     | $a$  | $b$ | $c$ | $d$ |
| ------------------------------- | ---- | --- | --- | --- |
| **Regular Spiking (RS)**        | 0.02 | 0.2 | -65 | 8   |
| **Intrinsically Bursting (IB)** | 0.02 | 0.2 | -55 | 4   |
| **Chattering (CH)**             | 0.02 | 0.2 | -50 | 2   |


These parameters define how quickly the recovery variable changes ($a$, $b$), how the membrane potential resets after a spike ($c$), and how much the recovery variable is increased after a spike ($d$).

Spiking Neural Network Implementation

In this project, a one-layer Spiking Neural Network (SNN) is implemented using Izhikevich neuron models. Each neuron is simulated using the Euler numerical method to solve the differential equations that describe the membrane potential and recovery dynamics.

The network receives the external input in the form of an applied current ($I$), which is first passed to the neurons as the initial input signal. After processing the current through the Izhikevich model equations, the neurons update their membrane potential ($v$), which is then used as the information transferred between neurons.

The Euler method is used to numerically solve the Izhikevich differential equations because these nonlinear systems generally cannot be solved analytically. The numerical solution obtained from the differential system represents the dynamic state of the neuron and is used as the activation mechanism of the SNN. Instead of traditional activation functions, the membrane potential evolution and spike generation determine the output behavior of each neuron.

## Spike Encoding and Decoding Algorithm

In this project, a spike encoding and decoding algorithm is used to transform continuous signals into spike-based representations and reconstruct the original information. As an example, the target function is:

$$
f(x)=x^2
$$

### Normalization

First, the input data is normalized to a suitable range for the neural system:

$$
x_{norm}=\frac{x-x_{min}}{x_{max}-x_{min}}
$$

### Spike Encoding

The normalized input is transformed into a firing frequency range between a minimum and maximum frequency:

$$
\alpha(x)=\alpha_{min}+x_{norm}(\alpha_{max}-\alpha_{min})
$$

where:

* $\alpha(x)$ is the generated firing frequency of the neuron.
* $\alpha_{min}$ is the minimum firing frequency.
* $\alpha_{max}$ is the maximum firing frequency.
* $x_{norm}$ is the normalized input value.

The generated frequency represents the number of spikes produced by the neuron during the current time interval. The spike contribution from each event is calculated using an exponential kernel:

$$
S(t)=e^{-\frac{|t-t_i|}{\tilde{t}}}W
$$

where:

* $t$ is the current time.
* $t_i$ is the spike time.
* $\tilde{t}$ is the time constant.
* $W$ is the synaptic weight of the connection.

### Spike Decoding

After processing through the SNN, the output spike frequency is converted back into a continuous value using the inverse frequency mapping:

$$
x_{decoded}=\frac{\alpha-\alpha_{min}}{\alpha_{max}-\alpha_{min}}
$$

The output is then transformed back to the original range:

$$
y_{out}=x_{decoded}(y_{max}-y_{min})+y_{min}
$$

### Error Calculation

The reconstructed output is compared with the desired function using Mean Squared Error:

$$
MSE=\frac{1}{N}\sum_{i=1}^{N}(y_i-\hat{y_i})^2
$$

where $y_i$ is the desired output and $\hat{y_i}$ is the reconstructed SNN output.

## Results and Observations

The performance of the different Izhikevich neuron types was evaluated using the Mean Squared Error (MSE) loss:


| Neuron Type                 | MSE    |
| --------------------------- | ------ |
| Regular Spiking (RS)        | 1.8344 |
| Intrinsically Bursting (IB) | 1.8486 |
| Chattering (CH)             | 1.8198 |
| Low Frequency + Chattering  | 1.7633 |


The results show that the **Chattering neuron provides the lowest error among the standard neuron types**, achieving better reconstruction accuracy compared to Regular Spiking and Intrinsically Bursting neurons. The combination of **Low Frequency and Chattering behavior achieves the lowest MSE**, indicating that this firing pattern provides the most suitable spike representation for the given task.

A possible explanation is that chattering neurons generate groups of closely spaced spikes, allowing them to represent detailed temporal information in the input signal. However, using an excessively high firing frequency can negatively affect performance because it may introduce redundant spikes, increase noise in the spike representation, and make decoding less accurate. A very high spike rate does not necessarily contain more useful information and can reduce the efficiency of the encoding process.

The Low Frequency + Chattering configuration provides a balance between temporal precision and spike efficiency. The lower firing rate prevents unnecessary spike generation, while the chattering behavior preserves important information through burst-based communication. This balance leads to a more accurate reconstruction of the original function and the lowest MSE value.


<p align="center">

<img src="https://img.shields.io/badge/SNN-red?style=for-the-badge">
<img src="https://img.shields.io/badge/AI-purple?style=for-the-badge">
<img src="https://img.shields.io/badge/Neuroscience-green?style=for-the-badge">
<img src="https://img.shields.io/badge/HH-orange?style=for-the-badge">
<img src="https://img.shields.io/badge/Izhikevich-blue?style=for-the-badge">
<img src="https://img.shields.io/badge/ActionPotential-yellow?style=for-the-badge">
<img src="https://img.shields.io/badge/Neuromorphic-brightgreen?style=for-the-badge">
<img src="https://img.shields.io/badge/EulerMethod-red?style=for-the-badge">
<img src="https://img.shields.io/badge/DifferentialSystems-purple?style=for-the-badge">
<img src="https://img.shields.io/badge/NeuronDynamics-green?style=for-the-badge">
<img src="https://img.shields.io/badge/SpikeEncoding-orange?style=for-the-badge">
<img src="https://img.shields.io/badge/SpikeDecoding-blue?style=for-the-badge">
<img src="https://img.shields.io/badge/NeuralCoding-yellow?style=for-the-badge">
<img src="https://img.shields.io/badge/BrainSimulation-brightgreen?style=for-the-badge">

</p>



---



# 🔍 Keywords and Topics

This project covers the following areas:

## 🧠 Computational Neuroscience
- Computational Neuroscience
- Biological Neuron Modeling
- Neural Dynamics
- Brain-Inspired Computing
- Neural Signal Processing

## ⚡ Spiking Neural Networks (SNN)
- Spiking Neural Network (SNN)
- SNN Simulation
- Spike-Based Computing
- Spike Trains
- Spike Encoding
- Spike Decoding
- Neural Coding
- Neural Information Processing
- Neuromorphic Computing

## 🤖 Artificial Intelligence and Machine Learning
- Artificial Intelligence (AI)
- Neural Networks (NN)
- Machine Learning
- Deep Learning
- Brain-Inspired Artificial Intelligence
- Biologically Inspired AI

## 🧬 Neuron Models
- Hodgkin–Huxley Model (HH Model)
- Hodgkin Huxley Equation
- Izhikevich Neuron Model
- Artificial Neurons
- Biological Neurons
- Regular Spiking (RS)
- Intrinsically Bursting (IB)
- Chattering Neurons

## ⚡ Neural Activity and Action Potentials
- Action Potential Simulation
- Membrane Potential
- Voltage Gated Ion Channels
- Sodium Channels ($Na^+$)
- Potassium Channels ($K^+$)
- Neuron Firing Patterns
- Spike Frequency Analysis

## 📊 Mathematical and Computational Methods
- Differential Equations
- Nonlinear Systems
- Euler Method
- Numerical Simulation
- Dynamical Systems
- Mean Squared Error (MSE)
- Signal Reconstruction

## 🔥 Main Technologies and Concepts
- Python Neural Simulation
- Computational Biology
- Neural Computation
- Synaptic Weights
- Frequency Encoding
- Frequency Decoding
- Spike-Based Learning
- Neural Model Comparison

  

---



<br>


<h2 align="center">Repository Tags</h2>

<p align="center">
SNN • Spiking Neural Network • AI • Neural Network • Computational Neuroscience • Hodgkin-Huxley • Izhikevich Model • Action Potential • Neuron Simulation • Spike Encoding • Spike Decoding • Neuromorphic Computing • Artificial Intelligence • Machine Learning • Brain Simulation
</p>

<br>

<p align="center">
Author: Mihaela Koseva (Михаела Косева)
</p>


<br>
<br>
<br>









<div align="center">

<a href="https://github.com/Dreamerol/VIZITKA" target="_blank">
  <img 
    src="https://raw.githubusercontent.com/Dreamerol/Dreamerol/main/!!!_MIHAELA_KOSEVA_VIZITKA_111.png"
    alt="Vizitka"
    width="100%"
  />
</a>

</div>





<br><br>







<h2 align="center">⭐ Feel free to explore repos and give a star if you find them interesting</h2>




<div align="center">

<p style="font-size:10px; line-height:1.6; letter-spacing:0.2px;">

Mihaela Koseva (Михаела Косева) • AI Engineer • Software Engineer • Backend Engineer • Data Systems & APIs • Applied Machine Learning • Deep Learning • Neural Networks • Model Training • Data Pipelines • LLMs • Python • C++ • Java • Clojure • SQL • PyTorch • TensorFlow • Scikit-learn • Pandas • NumPy • ETL • Data Modeling • MLOps

</p>

<p style="font-size:10px; opacity:0.7;">
🔗 Explore more on GitHub:
<a href="https://github.com/Dreamerol">Mihaela Koseva (Михаела Косева) • GitHub • Dreamerol</a>
</p>

</div>




<br>




---





<br>






<p align="center">

<a href="https://www.linkedin.com/in/mihaela-koseva-software-engineer">
  <img height="65" src="https://img.shields.io/badge/LINKEDIN-8A2BE2?style=for-the-badge&logo=linkedin&logoColor=white"/>
</a>

<a href="https://github.com/Dreamerol">
  <img height="65" src="https://img.shields.io/badge/GITHUB-9D4EDD?style=for-the-badge&logo=github&logoColor=white"/>
</a>

<a href="https://github.com/Dreamerol/PORTFOLIO">
  <img height="65" src="https://img.shields.io/badge/PORTFOLIO-6C63FF?style=for-the-badge&logo=github&logoColor=white"/>
</a>

<a href="https://github.com/Dreamerol/CARDFOLIO">
  <img height="65" src="https://img.shields.io/badge/REPOS-4F8CFF?style=for-the-badge&logo=github&logoColor=white"/>
</a>

<a href="https://github.com/Dreamerol/ALLSTATS">
  <img height="65" src="https://img.shields.io/badge/STATS-6C63FF?style=for-the-badge&logo=github&logoColor=white"/>
</a>

<a href="https://github.com/Dreamerol/RESUME">
  <img height="65" src="https://img.shields.io/badge/RESUME-9D4EDD?style=for-the-badge&logo=readthedocs&logoColor=white"/>
</a>


</p>





<br><br>





<div align="center">
  <a href="https://github.com/Dreamerol" target="_blank">
    <img
      src="https://raw.githubusercontent.com/Dreamerol/Dreamerol/main/MIHAELA%20KOSEVA_11.PNG"
      width="100%"
      alt="Mihaela Koseva Banner"
    />
  </a>
</div>







<br><br><br><br><br><br>



