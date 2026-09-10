
##  Project Overview

This project implements an AI-based Flappy Bird game using Reinforcement Learning.

The agent learns how to play the game automatically using Deep Q-Learning (DQN). Instead of controlling the bird manually, the AI learns which action to take based on the current game state and the reward received.

The main goal is to train an AI agent that can make better decisions and improve its gameplay through experience.


##  Objectives

* Implement a Flappy Bird game environment.
* Apply Reinforcement Learning to the game.
* Implement a Deep Q-Network (DQN).
* Train an AI agent to play the game automatically.
* Use Experience Replay to improve learning.
* Use a Target Network for stable training.
* Save the trained model for testing.

##  How the System Works

1. The Flappy Bird game environment is started.
2. The environment provides the current state of the bird and game.
3. The DQN model receives the state as input.
4. The agent selects an action using the Epsilon-Greedy strategy.
5. The agent can perform two actions:

   * `0` → No Flap
   * `1` → Flap
6. The environment returns a reward after the action.
7. The experience is stored in Replay Memory.
8. Random experiences are selected from Replay Memory for training.
9. The DQN learns to select better actions.
10. A Target Network is used to make training more stable.
11. Epsilon gradually decreases during training.
12. The trained model is saved for future testing.

##  Deep Q-Network (DQN)

The project uses a neural network called Deep Q-Network to select the best action.

### Network Architecture

* Input Layer: 12 state features
* Hidden Layer 1: 256 neurons
* Activation: ReLU
* Hidden Layer 2: 256 neurons
* Activation: ReLU
* Output Layer: 2 actions

The output represents the estimated Q-value for each possible action.

The action with the better Q-value can be selected by the agent.

##  Experience Replay

Experience Replay stores the agent's previous experiences in memory.

Each experience contains:

* Current state
* Action
* Reward
* Next state

During training, random experiences are selected from memory.

This helps the agent learn from past experiences and makes training more stable.

##  Epsilon-Greedy Strategy

The project uses an Epsilon-Greedy strategy for action selection.

* High epsilon → More exploration
* Low epsilon → More exploitation

At the beginning of training, the agent explores different actions.

As training continues, epsilon decreases and the agent uses its learned knowledge more often.

### Configuration

Initial Epsilon: 1.0
Minimum Epsilon: 0.05
Epsilon Decay: 0.9995

##  Target Network

The project uses a separate Target Network along with the main DQN.

The Target Network is updated periodically from the main network.

This helps reduce instability during training and improves the learning process.

##  Training Configuration

Environment: FlappyBird-v0

Initial Epsilon: 1.0
Minimum Epsilon: 0.05
Epsilon Decay: 0.9995

Replay Memory Size: 100000
Mini-Batch Size: 64

Network Sync Rate: 1000

Learning Rate: 0.0005
Discount Factor: 0.99

Reward Threshold: 1000


##  Technologies Used

* Python
* PyTorch
* Gymnasium
* Flappy Bird Gymnasium
* Pygame
* PyYAML

##  Project Structure

Flappy-bird-game/
 -agent.py
 -dqn.py
 -experience_replay.py
 -flappy_bird_game.py
 -parameters.yaml
 -.gitignore

### File Description

agent.py
Contains the main DQN agent, training process, testing process, reward calculation, model saving, and action selection.

dqn.py
Contains the Deep Q-Network neural network architecture.

experience_replay.py
Implements Replay Memory for storing and sampling past experiences.

flappy_bird_game.py
Runs the Flappy Bird environment with manual keyboard control.

parameters.yaml
Contains the training parameters and hyperparameters.

.gitignore
Prevents generated files such as model files, logs, cache files, and virtual environments from being uploaded to GitHub.

##  Installation

### 1. Clone the Repository

git clone https://github.com/pawasevaishnavi1-abc/Flappy-bird-game.git

### 2. Open the Project Folder

cd Flappy-bird-game

### 3. Create a Virtual Environment

python -m venv venv

### 4. Activate the Virtual Environment

For Windows:

venv\Scripts\activate

### 5. Install Required Libraries

pip install torch
pip install gymnasium
pip install flappy-bird-gymnasium
pip install pygame
pip install pyyaml

##  Training the Agent

To train the AI agent, run:

python agent.py flappybirdv0 --train

During training:

* The agent interacts with the game.
* Actions are selected using Epsilon-Greedy strategy.
* Experiences are stored in Replay Memory.
* The DQN is trained using sampled experiences.
* The Target Network is periodically updated.
* The best model is saved automatically.

##  Testing the Agent

After training, the saved model can be tested using:

python agent.py flappybirdv0

The game will open in render mode and the trained agent will play automatically.

##  Model Saving

The trained model is saved inside the `runs` folder.

runs/flappybirdv0.pt

Training logs are also stored in:

runs/flappybirdv0.log

The `runs` folder is ignored by Git so that generated model and log files are not unnecessarily uploaded to GitHub.

##  Learning Process

The AI agent improves through repeated interaction with the game.

During training:

1. The agent observes the game state.
2. It selects an action.
3. The game provides a reward.
4. The experience is stored.
5. The agent learns from previous experiences.
6. The DQN updates its knowledge.
7. The process continues for many episodes.

Through this process, the agent attempts to learn better actions for avoiding pipes and staying alive longer.

##  Future Improvements

* Improve training performance.
* Tune hyperparameters for better results.
* Improve the reward function.
* Train for more episodes.
* Add training performance graphs.
* Improve the DQN architecture.
* Experiment with Double DQN.
* Experiment with Dueling DQN.
* Add better visualization of the learning process.

##  Learning Outcomes

Through this project, I learned:

* Basics of Reinforcement Learning.
* Deep Q-Learning.
* Neural Network implementation using PyTorch.
* Epsilon-Greedy action selection.
* Experience Replay.
* Target Networks.
* Model training and saving.
* Working with Gymnasium environments.
* Using Git and GitHub for project management.

##  Author

Vaishnavi Pawase

B.E. Artificial Intelligence & Data Science

Amrutvahini College of Engineering, Sangamner

### GitHub

[GitHub Profile](https://github.com/pawasevaishnavi1-abc?utm_source=chatgpt.com)

### Project Repository

[Flappy Bird Game Repository](https://github.com/pawasevaishnavi1-abc/Flappy-bird-game?utm_source=chatgpt.com)

##  Acknowledgement

This project was developed as part of learning and implementing Reinforcement Learning, Deep Q-Learning, and Artificial Intelligence concepts using Python.
