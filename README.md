# Dueling DQN for Task Offloading in Mobile Edge Computing

![Build Status](https://img.shields.io/badge/build-passing-brightgreen)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange)
![NumPy](https://img.shields.io/badge/NumPy-1.x-green)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.x-blueviolet)
![License](https://img.shields.io/badge/License-MIT-yellow)

**Dueling DQN MEC** implements a Dueling Deep Q-Network with a Prioritized Replay Buffer to optimize task offloading decisions in a simulated Mobile Edge Computing (MEC) environment.  
The agent learns to balance **latency** and **energy consumption**, deciding whether to process tasks locally or offload them to nearby edge servers.

---

## 📌 Table of Contents
- [Problem Statement](#problem-statement)  
- [Key Features](#key-features)  
- [Architectural Overview](#architectural-overview)  
- [Technology Stack](#technology-stack)  
- [Getting Started](#getting-started)  
  - [Prerequisites](#prerequisites)  
  - [Install & Run](#install--run)  
- [Project Structure](#project-structure)  
- [Hyperparameters & Batching](#hyperparameters--batching)  
- [Results](#results)  
- [Contributing](#contributing)  
- [License](#license)  
- [Appendix — Quick Reference](#appendix--quick-reference)  

---

## 🧩 Problem Statement
In MEC, mobile devices can offload computation-heavy tasks to edge servers.  
- **Benefits:** Reduced latency, improved performance, extended battery life.  
- **Challenge:** Deciding *which tasks to offload* and *where to offload them* is complex.  

This project applies **Deep Reinforcement Learning (DRL)** to train an agent that makes **optimal real-time offloading decisions**.

---

## ✨ Key Features
- **Dueling DQN Agent** → Separates *value* and *advantage* streams for efficient Q-learning.  
- **Prioritized Replay Buffer** → Samples experiences with higher TD-error first to accelerate convergence.  
- **MEC Environment Simulator** → Configurable devices, edge servers, and tasks.  
- **Advanced Regularization** → L2 and dropout support in later versions (e.g., `dqn_v7`).  
- **Experiment Notebooks** → Step-by-step Jupyter notebooks for running training and visualizing results.  

---

## 🏗️ Architectural Overview

Agent–Environment loop:

+-------------------+ +------------------+
| Dueling DQN | | MEC Environment|
| Agent | | (Devices, |
| - Observes state | ----> | Servers, Tasks)|
| - Chooses action | | - Executes action|
+-------------------+ +------------------+
^ |
| Reward + New State |
+--------------------------+


Flow:
1. Agent observes state (devices, servers, tasks).  
2. Chooses an action → local processing or offloading.  
3. Environment executes → computes **energy cost** & **completion time**.  
4. Reward + new state returned.  
5. Agent updates its Q-policy to improve future choices.  

---

## ⚙️ Technology Stack
- **Language:** Python 3.8+  
- **Deep Learning:** TensorFlow 2.x (Keras API)  
- **Libraries:** NumPy, Matplotlib, tqdm (optional)  
- **Environment:** Jupyter Notebook  

---
