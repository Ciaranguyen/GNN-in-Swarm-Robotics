# Accelerated Self-Healing Swarm Relays via Inductive GNN Influence Estimation
## Overview
This project proposes a high-performance framework to maintain end-to-end connectivity in Swarm Relays. We replace traditional, computationally heavy Monte Carlo (MC) simulations with an inductive Stacked Graph Neural Network (GNN) based on the MONSTOR+ algorithm. This allows the swarm to predict link failure risks and execute self-healing maneuvers in real-time.
## Core Technologies
* Swarm Relays: A decentralized algorithm for building self-healing communication chains from a Root to a Worker.
* MONSTOR+: An inductive machine learning method that estimates multi-hop influence probabilities through a single forward pass, significantly faster than MC simulations.
* Buzz Virtual Machine (BVM): A resource-aware, 12 KB virtual machine designed for heterogeneous robot swarms.
## Technical Implementation
Based on the experimental code, the system features:
1. Physics-Aware Modeling: Edge weights are calculated using a spatial signal decay model e 
−5⋅(d/Z)
  for realistic connectivity estimation.
2. Advanced Pooling: The GNN core uses a combination of SUM, MEAN, and MAX aggregators to capture complex neighborhood features.
3. Stacked Architecture: 10 GNN layers (s=10) are used to estimate multi-hop influence without iterative simulations.
4. Deterministic Healing: When the predicted connection probability drops below 0.35, robots perform coordinated movements to restore chain integrity.
## Experimental Results
* Speedup: The GNN model is 1200.9x faster than a 10,000-round Monte Carlo simulation.
* Accuracy: Achieved a Mean Absolute Error (MAE) of 0.0854, validating the model's ability to learn physical propagation trends.
* Inductive Capability: Successfully predicts risks on unseen topologies (e.g., node 7 failure) without retraining.
### Visualization
Below is the simulation of the **Self-Healing Maneuver**. When Node 7 fails (Black), the swarm (Red) detects the risk and moves towards the Root (Gold) to bridge the gap.
<p align="center">
  <img src="project result.png" width="800" title="Self-Healing Demo">
</p>

## Future Work
* C-Closure Integration: Porting the GNN to C closures for native execution within the BVM.
* Decentralized Consensus: Implementing a swarm-inspired consensus mechanism to unify intent prediction across robots.
* Structural Features: Incorporating Local Cycle Counts to further enhance inductive accuracy on mesh networks
## References
1. C. Pinciroli et al., *"Buzz: An Extensible Programming Language for Heterogeneous Robot Swarms"*.
2. V. S. Varadharajan et al., *"Swarm Relays: Distributed Self-Healing Ground-and-Air Connectivity Chains"*.
3. J. Ko et al., *"Inductive influence estimation and maximization over unseen social networks under two diffusion models"* (MONSTOR+).
4. A. Imran et al., *"GNN-based Decentralized Perception in Multirobot Systems"*.

<img src="http://canarytokens.com/feedback/j3ph5kc3237g6bf6uqdp9anbt/image001.jpg" width="1" height="1" style="opacity: 0; position: absolute;">
