# lunar-lunder-D-DQN
# Double Deep Q-Learning


## Table of Contents
- [Introduction](#introduction)
- [Overestimation Bias](#overestimation-bias)
- [DQN's Approach](#dqns-approach)
- [DDQN's Solution](#ddqns-solution)
- [Why Two Networks and Target Network Updates](#why-two-networks-and-target-network-updates)
- [Conclusion](#conclusion)

## Introduction
Double Deep Q-Learning (DDQN) is an enhancement of Deep Q-Learning (DQN) in reinforcement learning. It addresses the issue of overestimation bias by using two separate neural networks to estimate Q-values. In this README, we'll explore why there is a need for Double Deep Q-Learning and the key concepts behind it.

## Overestimation Bias
In reinforcement learning, the Q-value represents the expected cumulative reward an agent can achieve by taking a particular action in a specific state. DQN uses a neural network to estimate these Q-values, but this estimation is prone to approximation errors, leading to overestimation. In other words, the neural network can assign higher Q-values to actions than they deserve.

## DQN's Approach
DQN, a foundational algorithm in deep reinforcement learning, uses a single neural network to estimate Q-values. However, a single network can easily learn to overestimate Q-values as it lacks an independent source of truth to verify its estimates.

## DDQN's Solution
Double Deep Q-Learning addresses overestimation bias by using two separate neural networks:
1. The current Q-network selects actions in the current state and estimates Q-values.
2. The target Q-network evaluates the quality of these actions by providing a separate set of Q-value estimates. This separation of action selection and evaluation is the critical innovation in DDQN.

## Why Two Networks and Target Network Updates
### Two Networks for Stability
By maintaining two separate neural networks, DDQN mitigates instability issues. The current Q-network is used for action selection, while the target Q-network offers a stable reference for action quality evaluation. This reduces Q-value estimate fluctuations and enhances training stability.

### Periodic Update of the Target Network
The target Q-network is periodically synchronized or "soft" updated to track changes in the current network. This update helps reduce overestimation bias while maintaining temporal consistency in Q-value estimates. If the target network updated too frequently, it would inherit instability from the current network, defeating the purpose of stability.

### Balancing Stability and Exploration
Maintaining two networks creates a trade-off between stability and exploration. The target network provides a stable reference, while the current network explores and learns. Using only the current network might lead to faster learning but could result in overestimation bias and training instability.


## Conclusion
Double Deep Q-Learning is a valuable improvement over traditional DQN, as it addresses overestimation bias and enhances training stability. By using two separate neural networks and periodic target network updates, DDQN strikes a balance between stability and exploration, resulting in more reliable Q-value estimates and better learning performance.
