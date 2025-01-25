DQN Hyperparameter Optimization for CartPole
This repository contains a Deep Q-Network (DQN) implementation for solving the CartPole problem using Optuna for hyperparameter optimization. The goal is to train an agent that can balance a pole on a cart by adjusting its actions based on the environment's state.

Overview
The main steps of the project involve:

Defining the CartPole environment: A custom environment based on OpenAI Gym's CartPole problem.
Building a Q-Network: A neural network that predicts Q-values for each action in the given state.
DQN Agent: An agent that uses Deep Q-Learning to select actions, store experiences in a replay buffer, and learn from these experiences.
Hyperparameter Optimization with Optuna: Using Optuna to tune the hyperparameters of the DQN agent to maximize the agent’s performance.
Training and Evaluation: After finding the best hyperparameters, the agent is trained for 500 episodes to evaluate its final performance.
