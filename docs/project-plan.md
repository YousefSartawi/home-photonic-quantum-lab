# Project Plan

## What I’m Building

This project is a small photonic quantum computing lab that I’m building from the ground up.

The plan is to start with a simple classical-light setup, use it to understand polarization control and measurement properly, then move toward real single-photon and two-photon experiments.

I’m doing the software and hardware together.

For each part of the system, I want to understand three things:

- the mathematics
- the software model
- what actually happens in the optical setup

The first version will not be a quantum computer. It is a learning platform that should give me enough control and understanding to build the real single-photon stages later.

---

## Current Stage

I’m currently working on:

**Stage 0 — Classical Polarization Trainer**

The planned setup is:

`Laser → Polarizer → HWP → QWP → PBS → Detectors → Computer`

This gives me a simple system where I can prepare a polarization state, change it, measure it, and compare the result against a software model.

The main goal at this stage is understanding the system properly, not adding complexity.

---

## Stage 0 — Classical Polarization Trainer

### What I want to learn

I’ll use this setup to work through:

- horizontal and vertical polarization
- qubit state vectors
- superposition
- relative phase
- measurement probabilities
- different measurement bases
- half-wave plates
- quarter-wave plates
- Bloch sphere rotations
- detector measurements

I also want to understand how the same operation looks in three different forms.

For example:

- as a matrix
- as Python code
- as a physical optical transformation

### Software

The first software will be simple.

I’ll build Python code that can:

- represent single-qubit states
- apply transformations
- calculate expected measurement probabilities
- model wave plates
- model polarization measurements
- compare predicted values with measured values

I’ll build this from basic NumPy first rather than relying only on a quantum SDK.

I’ll still use tools such as Qiskit as I continue learning quantum computing.

### Hardware

The first setup will use:

- low-power visible laser
- polarizer
- half-wave plate
- quarter-wave plate
- polarizing beam splitter
- two photodetectors
- computer or microcontroller for data collection

I’ll keep the system modular so that useful parts can be reused later.

### What counts as success

I should be able to prepare a known polarization state, change it in a predictable way, and measure the result.

The measured detector ratios should follow the values predicted by the software within reasonable experimental error.

I also want to measure practical things such as:

- repeatability
- drift
- extinction ratio
- alignment sensitivity

This stage uses classical light.

I will not describe it as a single-photon quantum computer.

---

## Stage 1 — Single-Photon System

Once Stage 0 is working reliably, the next step is moving to real single-photon experiments.

The basic idea is:

`Pump Laser → SPDC Crystal → Photon Pair`

One photon will be used as a herald.

The second photon will carry the state I want to prepare and measure.

A rough layout would be:

`Heralded Photon → HWP / QWP → PBS → SPAD Detectors → Timing Electronics`

This stage introduces several new problems that do not exist in the classical trainer:

- photon loss
- detector noise
- low count rates
- timing
- coincidence detection
- alignment
- source stability

The main goal here is to reliably prepare and measure a real single-photon polarization state.

---

## Stage 2 — Two-Photon System

The two-photon stage is where the setup starts becoming useful for proper multi-qubit experiments.

I want to work toward experiments involving:

- two-photon interference
- Bell states
- entanglement
- coincidence measurements
- state tomography
- Bell tests

The four basic two-qubit states are:

`|00⟩`

`|01⟩`

`|10⟩`

`|11⟩`

A later target would be an entangled state such as:

`(|00⟩ + |11⟩) / √2`

I’m treating a stable two-photon system as an important milestone.

If I can generate, measure, and characterise entanglement reliably, that gives me a real baseline for exploring more difficult ideas.

---

## Stage 3 — Scaling Research

The long-term part of the project is not simply about adding more photons.

That approach gets difficult quickly because every additional photon adds loss, alignment problems, detector requirements, and lower coincidence rates.

The research question I’m interested in is:

**How much controllable quantum state space can I create and measure with the fewest photons, detectors, and optical components?**

There are several directions I want to investigate.

### Multiple Degrees of Freedom

A photon can carry information in more than one way.

Possible degrees of freedom include:

- polarization
- path
- time-bin
- frequency

For example:

`polarization × path × time-bin`

gives:

`2 × 2 × 2 = 8`

possible basis dimensions.

That is the same Hilbert-space dimension as three qubits.

It does not automatically mean the system behaves like three independent qubits. The states still need to be prepared, controlled, and measured independently enough to be useful.

That is part of what I want to investigate.

### Time-Bin Encoding

Instead of adding more physical optical paths, I want to look at whether several time-separated modes can pass through shared hardware.

This may reduce the amount of physical hardware needed.

### Detector Multiplexing

Single-photon detectors are expensive.

One possible direction is routing several measurement outcomes through fewer detectors while keeping the outcomes distinguishable through timing or switching.

The question is whether this can reduce detector count without making the system too lossy or difficult to control.

### Qudits

I also want to study systems with more than two states per degree of freedom.

A four-state system has the same state-space dimension as two qubits, although the control and gate model are different.

### Automated Calibration

Optical systems drift.

Instead of manually realigning everything every time something changes, I want to investigate software-controlled calibration using motors, feedback, and optimisation.

That could include:

- automatic wave-plate adjustment
- phase correction
- drift compensation
- interference optimisation

This part fits closely with my software engineering background.

### Integrated Photonics

If the free-space setup becomes mature enough, I want to eventually move some of the design into integrated photonics.

The idea would be to design interferometers, phase shifters, and optical routing in software and then use fabricated photonic chips instead of building everything from separate components on a bench.

That is a long-term direction, not something I expect to do at the beginning.

---

## How I’ll Treat Experiments

I want to document the project like an engineering and research project rather than just a collection of demonstrations.

For each experiment I’ll try to record:

- what I’m testing
- the expected result
- the optical setup
- component settings
- raw measurements
- repeated trials
- uncertainty
- comparison with the theoretical model
- problems or limitations
- what I would change next time

Useful measurements may include:

- fidelity
- interference visibility
- optical loss
- coincidence rate
- stability
- detector count
- component count
- control complexity

The point is to measure whether an idea actually works.

---

## Software Direction

The software side will grow with the hardware.

For now I’ll focus on:

- Python
- NumPy
- state-vector simulation
- quantum gates
- measurement simulation
- polarization optics

Later this can expand into:

- Qiskit
- hardware control
- detector data acquisition
- time-tag processing
- tomography
- curve fitting
- uncertainty analysis
- automated calibration
- optimisation

I want the software to do more than produce diagrams.

Eventually it should control experiments, collect measurements, analyse results, and help keep the optical system calibrated.

---

## Immediate Work

Right now I’m keeping the scope small.

The next steps are:

1. Finish the basic single-qubit theory.
2. Build the single-qubit model in Python.
3. Model polarization and wave plates.
4. Finalise the Stage 0 optical layout.
5. Prepare the first bill of materials.
6. Buy the components.
7. Assemble the trainer.
8. Compare measured results against the software model.

I’ll only move to the single-photon stage once the first setup is stable and I understand what each component is doing.

---

## Safety

The first setup will use a low-power visible laser.

I’ll keep the beam controlled, avoid eye-level paths, use beam blocks where needed, and avoid direct or reflected exposure.

The later SPDC stage may require a higher-power pump laser.

I will not move into that stage until the setup has proper laser-safety controls and a defined alignment procedure.

---

## Long-Term Goal

The goal is not to build the largest setup possible.

I want to build the smallest setup that lets me understand and measure something useful.

Then I can use the limitations of that system to decide what to improve next.

The basic rule for the project is:

**Build it. Model it. Measure it. Understand where it fails. Then improve it.**