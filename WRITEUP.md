[image1]: https://user-images.githubusercontent.com/10624937/42135623-e770e354-7d12-11e8-998d-29fc74429ca2.gif "Tennis"
[image2]: https://github.com/cwiz/DRLND-Project-Collab-Compet/blob/master/images/Tennis.PNG?raw=true "Tennis-Rewards"
[image3]: https://github.com/cwiz/DRLND-Project-Collab-Compet/blob/master/images/Soccer-Striker.PNG?raw=true "Soccer-Rewards-Striker"
[image4]: https://github.com/cwiz/DRLND-Project-Collab-Compet/blob/master/images/Striker-Goalie.PNG?raw=true "Soccer-Rewards-Goalie"


# Project 3: Collaboration and Competition

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
 
### Soccer

**Goal**

* Experimentation environment

**Observation**

* Each agent receives observation vector of 130 containing positions of other agents and ball's position and velocity

**Actions**

* Striker: Discrete action space of 6 (move forward, move backward, move left, move right, rotate left, rotate right)
* Goalie: Discrete action space of 4 (move forward, move backward, move left, move right, rotate left)

**Rewards**

* Striker: reward for goal
* Goalie: reward for not getting ball in goal

## Project Goals

* Applying to Policy Gradient and self-play to zero-sum games with continuous observation and action space (Tennis)
* Extending approach for cooperation games (Soccer)

## Technical Formulation of Problem 

* Set up Environment as described in [Project Repository](https://github.com/udacity/deep-reinforcement-learning/tree/master/p3_collab-compet)
* Complete Tennis.ipynb 
* [optional] Complete Soccer.ipynb 

## Mathematical Models

All mathematical models are taken directly from previous work [1]. Soccer environment uses 2 neural networks for each kind of agent. Soccer uses discrete version of actor critic.

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

### Soccer

#### Hyperparameters

```python
LR = 3e-3
GAMMA = 0.99
BATCH_SIZE = 256
BUFFER_SIZE = int(1e6)
ALPHA = 0.1
TAU = 0.05
TARGET_UPDATE_INTERVAL = 1
GRADIENT_STEPS = 1
```

#### Rewards plot

##### Striker

![Soccer-Rewards-Striker][image3]

##### Goalie

![Soccer-Rewards-Striker][image4]

## Future Work

Results for cooperation game (Soccer) are hard to quantify. Subjectively agents discover initial strategy to shoot the ball in direction of opponent's goal in beginning of match, but many times don't use opportunities if ball bounces off. Explanation might be that training time is not sufficient or bad choice of algorithm.

## References

[1] Sergei Surovtsev, Using Policy Optimization (PO) Algorithms Soft Actor-Critic (SAC) and Proximal Policy Optimization (PPO) for Solving Unity ML Reacher and Crawler Continous Control Environments, 2019, https://github.com/cwiz/DRLND-Project-Continuous_Control/blob/master/WRITEUP.md
