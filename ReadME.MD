# Hands-on with SynSense Speck™

Hands-on material for exploring **event-based vision and spiking neural networks (SNNs) on the SynSense Speck™ neuromorphic platform**.

This repository contains the material accompanying the *Hands-on with Speck* session, including the presentation, example code, and event-based video data.

## Overview

Conventional vision systems continuously capture and process complete image frames. Event-based cameras take a different approach: they asynchronously report changes in brightness as individual events.

The **SynSense Speck™** platform combines an event-based vision sensor with neuromorphic processing hardware, making it possible to process visual information using asynchronous, spike-based computation directly on the edge.

This hands-on introduces the complete workflow from **event-based input to spiking neural network inference on neuromorphic hardware**.

The main topics include:

* Event-based vision and Dynamic Vision Sensors (DVS)
* Event streams and their representation
* Spiking neural networks
* Neuromorphic vision processing
* Developing and testing SNNs
* Running event-based workloads on Speck™
* Understanding the relationship between sparsity, accuracy, latency, and energy efficiency

## Repository contents

```text
.
├── codes/
│   └── ...
├── Hands-On-Mazdak-Fatahi.pdf
├── nmnist.mkv
└── README.md
```

### `Hands-On-Mazdak-Fatahi.pdf`

The presentation and step-by-step material used during the hands-on session.

[Open the presentation](./Hands-On-Mazdak-Fatahi.pdf)

### `codes/`

Source code and examples used during the exercises.

The examples are intended to illustrate the development and deployment workflow rather than provide a complete production-ready application.

### `nmnist.mkv`

An event-based video used as an input example for the hands-on exercises.

## Learning objectives

After completing the hands-on, you should have a practical understanding of how to:

1. Work with event-based visual data.
2. Represent and process asynchronous events.
3. Build or adapt a spiking neural network for event-based vision.
4. Evaluate an SNN before hardware deployment.
5. Deploy an SNN to neuromorphic hardware.
6. Examine the effect of event sparsity and network parameters on performance.
7. Understand the trade-offs between **accuracy, latency, computation, and energy consumption** in event-driven systems.

## Event-based vision

Unlike conventional cameras, a DVS does not produce a sequence of complete image frames.

Instead, each pixel independently generates an event when it detects a sufficient change in brightness. An event can be represented as:

```text
(x, y, t, p)
```

where:

* `x` – horizontal pixel coordinate
* `y` – vertical pixel coordinate
* `t` – timestamp
* `p` – event polarity

This asynchronous representation naturally produces sparse data, particularly when the visual scene is mostly static.

The resulting event stream can be processed directly by spiking neural networks, making event-based vision particularly suitable for low-latency and energy-efficient neuromorphic systems.

## SynSense Speck™

Speck™ is a neuromorphic vision System-on-Chip combining an event-based vision sensor with asynchronous spiking neural processing.

The platform is designed for real-time, always-on vision applications where low latency and low power consumption are important.

The hands-on therefore focuses not only on whether a neural network produces the correct result, but also on how efficiently it processes an event stream.

## Hands-on workflow

The exercises follow the general pipeline:

```text
Event-based data
       │
       ▼
Event representation / preprocessing
       │
       ▼
Spiking Neural Network
       │
       ├── Software simulation
       │
       └── Speck™ hardware
              │
              ▼
       Performance evaluation
```

The software stage allows the network to be developed and evaluated before deployment. The hardware stage demonstrates how the same event-driven computation can be executed on neuromorphic hardware.

## Performance considerations

For neuromorphic systems, classification accuracy is only one part of the evaluation.

The hands-on also considers:

* **Latency** – how quickly the system responds to an event stream
* **Sparsity** – how many events are actually processed
* **Energy consumption** – the cost of performing the computation
* **Throughput** – how much event data can be processed
* **Model complexity** – the computational and hardware resources required

These metrics illustrate an important characteristic of neuromorphic computing: reducing unnecessary computation can be as important as improving the neural network itself.

## Getting started

Clone the repository:

```bash
git clone https://github.com/MazdakFatahi/Hands-on-with-Speck.git
cd Hands-on-with-Speck
```

Then explore the presentation:

```text
Hands-On-Mazdak-Fatahi.pdf
```

and the examples under:

```text
codes/
```

### Hardware

Some exercises require access to a **SynSense Speck™ development platform**. Software-only parts of the hands-on can be followed without the physical hardware, while hardware deployment and measurements require a compatible Speck™ device and its software environment.

## Prerequisites

A basic understanding of the following topics is helpful:

* Python programming
* Neural networks
* Spiking neural networks
* Event-based vision

No previous experience with Speck™ is required.

## Further resources

* [SynSense Speck™](https://www.synsense.ai/products/speck-2/)
* [SynSense](https://www.synsense.ai/)
* [Sinabs](https://sinabs.readthedocs.io/)
* [Neuromorphic Platform – Université de Lille](https://gitlab.univ-lille.fr/bioinsp/neuromorphic-platform)

## Citation

If you use this material in a workshop, course, presentation, or research project, please refer to the original hands-on material:

**M. Fatahi, "Hands-on with Speck", Université de Lille / IRCICA.**

## Author

**Mazdak Fatahi**
Research Engineer — Université de Lille
Neuromorphic Computing & Event-Based AI

GitHub: [MazdakFatahi](https://github.com/MazdakFatahi)

---

*This repository is intended for educational and research purposes.*
