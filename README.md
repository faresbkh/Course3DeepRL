# Project 2: Continuous Control

[image1]: https://user-images.githubusercontent.com/10624937/43851024-320ba930-9aff-11e8-8493-ee547c6af349.gif "Trained Agent"
[image2]: https://user-images.githubusercontent.com/10624937/43851646-d899bf20-9b00-11e8-858c-29b5c2c94ccc.png "Crawler"
### Introduction

For this project, you will work with the [Reacher](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#reacher) environment.

![Trained Agent][image1]

In this environment, a double-jointed arm can move to target locations. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of your agent is to maintain its position at the target location for as many time steps as possible.

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.

### Getting Started

1. Download the environment from one of the links below.  You need only select the environment that matches your operating system:
    - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux.zip)
    - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher.app.zip)
    - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86.zip)
    - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86_64.zip)

    (_For Windows users_) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

    (_For AWS_) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux_NoVis.zip) (version 1) or [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux_NoVis.zip) (version 2) to obtain the "headless" version of the environment.  You will **not** be able to watch the agent without enabling a virtual screen, but you will be able to train the agent.  (_To watch the agent, you should follow the instructions to [enable a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md), and then download the environment for the **Linux** operating system above._)


2. Place the file in the course GitHub repository, in the base folder, and unzip (or decompress) the file. Ib the `Continuous_Control_solution.ipynb` change the cell 
    ```python
   env = UnityEnvironment(file_name="Reacher_Windows_x86_64_20\Reacher.exe")
   ```
   with the file name and folder corresponding to your operating system

### Description

*   The complete code is inside the `Continuous_Control_solution.ipynb` running the cells in order will 
    *   Create the environment ( do not close unity window if it stays loading for too long as you need to run the other cells while it's open )
    *   Define the Actor and Critic
    *   Define the Agent an initialise it
    *   Define ddpg algoritm
    *   Train the agents
    *   Explore the result
    *   Test the model in inference mode
    *   Close the environment ( this will close the unity window )
*   The base implementation is based on `deep-reinforcement-learning` [implementation](https://github.com/udacity/deep-reinforcement-learning/tree/master/ddpg-pendulum) of ddpg 
*   This repo contains these files :
    - `cgeckpoint.pth`: saved model weights for the Double DQN model
    - `Continuous_Control_solution.ipynb`: notebook containing the solution
    - `scores_plot.png`: score evolution during training of the model
*   To run the project the dependencies required are in the `requirements.txt` file with instructions how to create conda environment, One major difference is the Torch version as the oldest available version of torch in python 3.6 currently is 1.7.0 which is different from the recommended version. Also torch gpu version is installed.