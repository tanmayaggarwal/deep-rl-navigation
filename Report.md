# Author: Tanmay Aggarwal

# Project Navigation

### Overview

In this project, I use the Deep Q-Learning algorithm to train an agent to collect yellow bananas in the Unity environment. There are three main files in this project:
1. Navigation.ipynb
2. dqn_agent.py
3. model.py_

The Jupyter Notebook 'Navigation.ipynb' is the main file used to train and run the agent. The following macro parameters are used in the training process:
- n_episodes: 2000
- max_t: 1000
- eps_start: 1.0
- eps_end: 0.01
- eps_decay: 0.995

The 'dqn_agent.py' file is used to define the Agent class as well as the ReplayBuffer class. The following hyperparameters are used in the training process:

- BUFFER_SIZE = 1e5               # replay buffer size
- BATCH_SIZE = 64                 # minibatch size
- GAMMA = 0.99                    # discount factor
- TAU = 1e-3                      # for soft update of target parameters
- LR = 5e-4                       # learning rate
- UPDATE_EVERY = 4                # how often to update the network

The 'model.py_' file is where the neural network model is defined. This neural network is being used as the function approximator that guides the agent's actions at each time step (i.e., the policy).

The overall architecture of the model is relatively simple with two fully connected hidden layers with 64 nodes each. ReLU activation function is used in between each layer in the network.

An Adam optimizer is used to minimize the loss function. I have used the Mean Squared Error loss function in this model.

### Plot of Rewards

The environment is solved (i.e., the average score of 13 is reached) in 431 episodes.

![Rewards Image](/Plot_of_Rewards.png)

### Future improvements

The following future improvements to this agent should be considered to further improve effectiveness of the agent (i.e., get a higher average score and / or lower training time):
1. Using a double DQN to eliminate overestimation bias for the action values
2. Using a prioritized experience replay buffer to focus learning from those experiences that offer more learning opportunities to the agent (both positive or negative).
