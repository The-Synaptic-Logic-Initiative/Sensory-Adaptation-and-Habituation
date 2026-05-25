# 🧠 Sensory Adaptation & Habituation Simulator

An interactive, browser-based neural network simulation demonstrating **Sensory Habituation** and **Spontaneous Recovery**. Watch artificial neurons visually "tire out" as they process repeated stimuli, dimming in real-time, and watch them light back up when allowed to rest.

![Zero Dependencies](https://img.shields.io/badge/Dependencies-0-brightgreen)
![Vanilla JS](https://img.shields.io/badge/Tech-Vanilla_JavaScript-f7df1e)
![HTML5 Canvas](https://img.shields.io/badge/Render-HTML5_Canvas-e34f26)

> *Ever wonder why you stop noticing the hum of an air conditioner after a few minutes, but immediately jump if it makes a sudden clanking noise? This is sensory habituation and dishabituation in action.*

---

## 🎯 What is this?

This project models how biological sensory systems filter out repetitive, non-threatening information to save energy. Instead of a static textbook diagram, this is a live, dynamic environment where you control the stimulus.

The network consists of three layers (Input, Hidden, Output). As you fire stimuli into the network, you can physically see the response diminish. The glowing neurons fade to gray, and the synaptic connections weaken. If you pause the stimulus, the neurons undergo spontaneous recovery. 

### ✨ Features

* **Live Canvas Rendering:** Neurons glow amber based on their current response strength and dim to gray as they habituate.
* **Dishabituation (Novel Stimulus):** Fire a "Novel Stimulus" to see a purple flash that immediately jolts the network out of its habituated state, resetting response strengths.
* **Real-Time Oscilloscope:** A live-scrolling graph tracking the exact output response of the network over time.
* **Dynamic Parameters:** Tweak the Habituation Rate ($\alpha$), Recovery Rate ($\beta$), and Stimulus Frequency live to see how different organisms or sensory modalities might react to noise.
* **Auto-Stimulation & Rest Modes:** Set the network to auto-fire at a specific Hz, or force it to sleep to watch the mathematical recovery curve.

---

## 🔬 The Science (The Math Under the Hood)

This simulator does not use traditional machine learning backpropagation. Instead, it uses a time-dependent biological decay model. Each neuron has a `response` value ($R$) ranging from $0$ to $1.0$.

**1. Habituation (Stimulus Hit)**
When a neuron receives a stimulus, its response drops based on the Habituation Rate ($\alpha$):
$$R \leftarrow R \times (1 - \alpha)$$

**2. Spontaneous Recovery (Time Decay)**
Every single animation frame, the neuron slowly climbs back to its baseline resting state ($1.0$), governed by the Recovery Rate ($\beta$):
$$R \leftarrow R + (1 - R) \times \beta$$

This creates a dynamic equilibrium. If the stimulus fires faster than the neuron can recover, the signal dies out. If a novel stimulus is introduced, it bypasses the habituated pathways and resets the response strength.

---

## 🚀 Getting Started

This project is built with **100% Vanilla HTML, CSS, and JavaScript**. There is no backend, no Webpack, and no `node_modules`. 

1. Clone the repository:
   ```bash
   git clone [https://github.com/yourusername/sensory-habituation-sim.git](https://github.com/yourusername/sensory-habituation-sim.git)

2. Open the directory on your machine.
3. 3. Navigate to the project folder on your local machine.
4. Double-click the `habituation_simulator.html` file to launch it directly in your preferred web browser.
5. Hit **Send Stimulus** and watch the habituation begin!

---

## 🛠️ Tech Stack Architecture

* **⚙️ Logic Engine:** Pure Vanilla JavaScript powered by a highly optimized `requestAnimationFrame` loop.
* **🎨 Network Rendering:** Native HTML5 `<canvas>` API, utilizing dynamic radial gradients, reactive node glows, and variable-opacity connecting lines.
* **📈 Graph Rendering:** A secondary HTML5 `<canvas>` implementation dedicated to the real-time, scrolling area chart.
* **💅 UI/UX Design:** Modern, dependency-free CSS leveraging custom properties (variables), Flexbox/Grid layouts, and a sleek glassmorphic aesthetic.

---

## 🤝 Contributing

We love community input! Contributions, bug reports, and feature requests are highly encouraged. Whether you want to introduce *sensitization* mechanics or map specific biological decay rates (e.g., auditory versus olfactory habituation), we'd love to see it. 

Feel free to check the [Issues page](https://github.com/yourusername/sensory-habituation-sim/issues) to start a discussion or simply open a Pull Request.

---

## 📝 License

This project is released under the [MIT License](https://choosealicense.com/licenses/mit/). Feel free to use, modify, and distribute this code as you see fit.
