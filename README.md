[//]: # "Image References"

[image1]: https://user-images.githubusercontent.com/10624937/43851024-320ba930-9aff-11e8-8493-ee547c6af349.gif "Trained Agent"



# Project 2: Continuous Control

### Introduction

tasThe content in this repository was created in order to accomplish the second project assignment of Udacity's [Deep Reinforcement Learning Nanodegree](https://www.udacity.com/course/deep-reinforcement-learning-nanodegree--nd893) and is utilizes Unity's  [Reacher](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#reacher) environment using 20 parallel agents.


#### Objective
The task is to control 20 instances of a double-jointed arm in order to follow a moving target.

![Trained Agent][image1]


#### Action Space
The action space is 4-dimensional for each instance of the double-jointed arm and corresponds to the the normalized torque (numbers between -1 and 1) that is to be applied to each of the two joints.

#### Observation Space

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm.


#### Reward
A reward of +0.1 is provided for each step that the agent's hand is in the goal location.

#### Goal
The training of the Agents is over, once an average reward of +30 over 100 consecutive episodes is obtained, where the reward for each episode is averaged over all Agents.



### Dependencies

#### Files
- `Continous_Control.ipynb`	(Main file for training.)
- `DDPG_Agent.py` (Deep deterministic policy gradient (DDPG) agent)
- `model.py` (Actor and critic network.)
- `checkpoint_actor.pth` (weights of trained actor network)
- `checkpoint_critic.pth` (weights of trained critic network)
- `Validate_Continous_Control.ipynb` (Visualizes a smart agent.)

#### Environments

##### Anaconda Environment

Follow the instructions in https://github.com/udacity/deep-reinforcement-learning section **Dependencies** to set up the anaconda environment.


##### Unity Environment

1. Download and unpack the environment for your operating system from the links below:

- Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux.zip)
- Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher.app.zip)
- Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86.zip)
- Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86_64.zip)

See https://github.com/udacity/deep-reinforcement-learning/tree/master/p2_continuous-control/README.md for further information.

2. Set the path to the environment binary in `Continous_Control.ipynb` (code cell 2) according to your environment. For example:
    ```python
    env = UnityEnvironment(file_name="Reacher_Linux/Reacher.x86_64")
    ```


#### Getting Started
For training run `Continous_Control.ipynb`. For validation instantiate an agent from `DDPG_Agent.py` and load actor and critic weights as follows or simply run `Validate_Continous_Control.ipynb` for watching a smart agent.
```python
agent.actor_local.load_state_dict(torch.load('checkpoint_actor.pth'))
agent.critic_local.load_state_dict(torch.load('checkpoint_critic.pth'))
```

