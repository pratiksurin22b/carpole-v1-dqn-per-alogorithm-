Dueling DQN for Task Offloading in Mobile Edge Computing
This repository contains a collection of experiments and models for optimizing task offloading in a Mobile Edge Computing (MEC) environment using Deep Reinforcement Learning. The primary approach explored is the Dueling Deep Q-Network (DQN) with a Prioritized Replay Buffer, which has been shown to improve the task offloading process in a simulated environment, providing better offloading speeds.

Table of Contents
Problem Statement

Key Features

Architectural Overview

Technology Stack

Getting Started

Prerequisites

Running the Application

Project Structure

Results

Contributing

License

Problem Statement
In Mobile Edge Computing, offloading tasks from mobile devices to nearby edge servers can significantly improve performance and save battery life. However, deciding which tasks to offload and to which server is a complex optimization problem. This project tackles this challenge by using Deep Reinforcement Learning to train an intelligent agent that can make optimal offloading decisions in real-time.

Key Features
Dueling DQN Agent: The core of this project is a Dueling DQN agent designed to learn the optimal policy for offloading tasks in the MEC environment. Its architecture separates the value and advantage streams, enabling more efficient learning and superior performance.

Mobile Edge Computing (MEC) Environment: The project includes a simulated MEC environment that models the key components of a real-world MEC system, including mobile devices, edge servers, and tasks. The environment is highly configurable, allowing you to experiment with different parameters and scenarios.

Prioritized Replay Buffer: To improve the agent's learning efficiency, a Prioritized Replay Buffer is used to store and sample experiences. This technique prioritizes experiences that are more informative, allowing the agent to learn from its mistakes and converge to a better policy more quickly.

Architectural Overview
The system is composed of a Deep Reinforcement Learning agent that interacts with a simulated Mobile Edge Computing environment.

Dueling DQN Agent: The agent observes the state of the MEC environment, which includes information about the mobile devices, edge servers, and the current task.

MEC Environment: The environment receives an action from the agent (i.e., whether to process a task locally or offload it to an edge server).

Action Execution: The environment executes the action and calculates the resulting energy consumption and task completion time.

Reward and State Update: The environment provides the agent with a reward based on the outcome of the action and updates the state of the system.

Learning: The agent uses the reward and the new state to update its policy, learning to make better decisions over time.

Technology Stack
Language: Python 3

Deep Learning Framework: TensorFlow

Libraries: NumPy, Matplotlib

Getting Started
Follow these instructions to get the project running on your local machine.

Prerequisites
Make sure you have the following software installed:

Python 3

TensorFlow

NumPy

Matplotlib

Running the Application
Clone the repository:

Bash

git clone <your-repository-url>
cd carpole-v1-dqn-per-alogorithm-
Explore the Notebooks:
The repository is organized into several directories, each containing a different version of the DQN model or a related experiment. The main files to look at are:

New Models/latest_dqn_v2.ipynb: This notebook contains the latest version of the Dueling DQN agent with a Prioritized Replay Buffer.

dqn_v7/dqn_v7.ipynb: This notebook contains a more advanced version of the DQN model with several improvements, including L2 regularization and dropout layers.

Run the Experiments:
To run the experiments, simply open the notebooks in Jupyter and run the cells. The notebooks are well-commented and should be easy to follow.

Project Structure
The project is organized into several directories, with each containing a different version of the DQN model or a related experiment.
carpole-v1-dqn-per-alogorithm-/
├── DQN_Comparision/            # Notebooks comparing different DQN models
├── Earlier models/             # Earlier versions of the DQN model
├── Energy_tracker_algo/        # Models with a focus on energy tracking
├── New Models/                 # The latest and most advanced models
│   ├── latest_Dqnv1.ipynb
│   └── latest_dqn_v2.ipynb
├── dqn_v3/
├── dqn_v4/
├── dqn_v5/
├── dqn_v6/
└── dqn_v7/
└── dqn_v7.ipynb            # Advanced DQN with regularization and dropout

Results
The results of the experiments are documented in the DQN Project Graphs.docx and DQN Project Graphs(With hyperparameter tuning).docx files. These documents contain several graphs that show the performance of the different DQN models in terms of training rewards, task completion rates, and energy consumption.

Here are some of the key findings from the experiments:

The Dueling DQN agent with a Prioritized Replay Buffer significantly outperforms a baseline DQN model in terms of both task completion rate and energy consumption.

Hyperparameter tuning has a significant impact on the agent's performance. The best results were obtained with a learning rate of 0.005, a batch size of 128, and an epsilon decay of 0.998.

The use of L2 regularization and dropout layers in the dqn_v7 model helps to prevent overfitting and improve the agent's generalization performance.