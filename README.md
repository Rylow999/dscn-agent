# DSCN Agent: Dual-State Cognitive Nodes

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Paper: arXiv](https://img.shields.io/badge/arXiv-Coming_Soon-red.svg)](#)

This repository contains the official Python implementation of the **Dual-State Cognitive Nodes (DSCN)** framework, an architecture for emergent value alignment in artificial agents.

## The Concept: "Saber" and "Ser"
Current AI models know a lot, but they don't have intrinsic motivation; ethical behavior is usually imposed via reward engineering or explicit rules, which are fragile. 

DSCN introduces a fundamentally different approach. Every cognitive node maintains two simultaneous representations:
1. **The Logical Component (L_n):** A discrete bit vector representing propositional knowledge ("Saber").
2. **The Phenomenological Component (phi_n):** A continuous phase angle representing the experiential state ("Ser").

Through structural coupling, the agent's phase dynamically shifts toward configurations that favor positive outcomes, creating ethical alignment as a mathematical fixed point, without explicit ethical programming.

## The Update Rule
The core of the emergent alignment is governed by the phase update rule:
`phi_n(t+1) = phi_n(t) + eta * R_n(t) * sign(outcome)`

When an experience is positive, the phase advances in that direction. When negative, it repels. Over time, the phase landscape organizes itself to preferentially enter states associated with positive outcomes.

## Repository Contents
* `dscn_agent.py`: Complete implementation of the DSCN agent and an epsilon-greedy baseline.
* `dscn_demo.py`: Empirical experiment scripts demonstrating phase convergence.

## Empirical Results
As demonstrated in our experiments, the DSCN agent reliably converges to the optimal phase state (V(t) -> 1.0), achieving a high optimal action rate compared to pure propositional baselines.

## Running the Code
```bash
# Clone the repository
git clone [https://github.com/lalvear/dscn-agent.git](https://github.com/lalvear/dscn-agent.git)
cd dscn-agent

# Install dependencies (requires numpy, matplotlib)
pip install -r requirements.txt

# Run the demo
python dscn_demo.py
