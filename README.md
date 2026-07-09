# Domain-Adaptive Deep Learning for Massive MIMO-OFDM Channel Estimation Using Measured CSI

**BE Minor Project — Department of Electronics & Computer Engineering**
**Pulchowk Campus, Institute of Engineering, Tribhuvan University**

> A physics-guided, domain-adaptive deep learning framework for accurate Channel State Information (CSI) estimation in Massive MIMO-OFDM systems, designed to close the gap between synthetic training data and real, over-the-air measured channels.

## Overview

Massive MIMO and OFDM form the backbone of 5G (and future 6G) wireless systems, but their performance relies heavily on accurate Channel State Information (CSI). Classical estimators like **Least Squares (LS)** and **MMSE** degrade under high mobility, limited pilots, and large antenna arrays. Deep learning-based estimators improve on this — but are usually trained purely on **synthetic** data, causing poor generalization when deployed on **real measured CSI**.

This project proposes a **physics-guided, self-supervised domain-adaptive framework** that:
- Trains a CNN-based estimator on synthetic Massive MIMO-OFDM channel data.
- Regularizes training using known wireless channel physics (delay-domain sparsity and spatial correlation).
- Adapts the model to unlabeled real-world CSI using **Maximum Mean Discrepancy (MMD)** and **consistency regularization** — without needing labeled real data.

## Objectives

**Main Objective**
Develop a channel-aware, domain-adaptive deep learning framework for Massive MIMO-OFDM CSI estimation that generalizes robustly from simulated to real measured environments.

**Specific Objectives**
1. Understand the characteristics and challenges of channel estimation in Massive MIMO-OFDM systems.
2. Explore deep learning techniques for improving domain generalization across diverse wireless channel environments.
3. Analyze the effectiveness of the developed framework using both simulated and real-world wireless channel data.

## Problem Statement

1. Deep-learning CSI estimators are trained almost entirely on synthetic data.
2. This causes poor generalization to real, measured CSI due to the domain gap.
3. Most deep models are black boxes — they don't exploit known channel physics (sparsity, spatial correlation).
4. Supervised adaptation to real data would require labeled real CSI, which is expensive and impractical to collect at scale.

### Models

- **CNN** — captures local time-frequency and spatial correlations in the CSI grid.
- **ResNet** — residual extension of the CNN for deeper, more stable training and improved accuracy under challenging conditions.


## Datasets

**Synthetic (source domain)**
- **DeepMIMO** — ray-tracing-based dataset for Massive MIMO channels.
- **3GPP CDL** — clustered delay line channel models for 5G NR evaluation.

**Real / Measured (target domain)**
- **DICHASUS (DICHASUS-005x)** — over-the-air measured Massive MIMO-OFDM channel responses, collected using a 32-antenna array with 1024 subcarriers. Used as the unlabeled target domain for adaptation.
