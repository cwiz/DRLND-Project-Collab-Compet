[image1]: https://user-images.githubusercontent.com/10624937/42135623-e770e354-7d12-11e8-998d-29fc74429ca2.gif "Tennis"
[image2]: https://github.com/cwiz/DRLND-Project-Collab-Compet/blob/master/images/Capture.PNG?raw=true "Tenis-Rewards"


# Project 2: Collaboration and Competition

**Sergei Surovtsev**
<br/>
Udacity Deep Reinforcement Learning Nanodegree
<br/>
Class of May 2019

## Project Description
This project is about applying policy optimization algorithms to master zero-sum game of Tennis with self-play in Unity Environment.

### Tennis

![Tennis][image1]

**Goal**

* Achieve average score over 0.5 over 100 episodes

**Observation**

* 8 variables corresponding to the position and velocity of the ball and racket

**Actions**

* Continuous vector space for moving forward and jumping

**Rewards**

* If an agent hits the ball over the net, it receives a reward of +0.1
* If an agent lets a ball hit the ground or hits the ball out of bounds, it receives a reward of -0.01
 
### [optional] Soccer

## Project Goals

* Applying to Policy Gradient and self-play to zero-sum games with continuous observation and action space (Tennis)
* [optional] Extending approach for cooperational games (Soccer)

## Technical Formulation of Problem 

* Set up Environment as described in [Project Repository](https://github.com/udacity/deep-reinforcement-learning/tree/master/p3_collab-compet)
* Complete Tennis.ipynb 
* [optional] Complete Soccer.ipynb 

## Mathematical Models

All mathematical models are taken directly from previous work [1]. For Soccer environment this work uses Soft-Actor Critic.

## Neural Networks

Tennis environment uses the same network used to solve environments from previous work. [1]

## Results

### Tennis

#### Hyperparameters

```python
NET_SIZE = 128
LR = 3e-4
GAMMA = 0.99
BATCH_SIZE = 256
BUFFER_SIZE = int(1e6)
ALPHA = 0.2
TAU = 0.005
TARGET_UPDATE_INTERVAL = 1
GRADIENT_STEPS = 1
```

#### Rewards plot

![Tennis-Rewards][image2]

### [optional] Soccer

#### Hyperparameters

#### Rewards plot

## Future Work

## References

[1] Sergei Surovtsev, Using Policy Optimization (PO) Algorithms Soft Actor-Critic (SAC) and Proximal Policy Optimization (PPO) for Solving Unity ML Reacher and Crawler Continous Control Environments, 2019, https://github.com/cwiz/DRLND-Project-Continuous_Control/blob/master/WRITEUP.md
