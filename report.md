

## Environment

We work with the Reacher environment

Set-up: Double-jointed arm which can move to target locations.
Goal: The agents must move its hand to the goal location, and keep it there.
Agents: The environment contains 10 agent linked to a single Brain.
Agent Reward Function (independent):
+0.1 Each step agent's hand is in goal location.
Brains: One Brain with the following observation/action space.
Vector Observation space: 26 variables corresponding to position, rotation, velocity, and angular velocities of the two arm Rigidbodies.
Vector Action space: (Continuous) Size of 4, corresponding to torque applicable to two joints.
Visual Observations: None.
Reset Parameters: Two, corresponding to goal size, and goal movement speed.
Benchmark Mean Reward: 30

## Algorithm

DDPG is an actor-critic, model-free algorithm based on the deterministic policy gradient that can operate over continuous action spaces as described in the Continuous control with deep reinforcement learning paper (https://arxiv.org/abs/1509.02971)

![ddpg](/image/ddpg.png)
#### hyperparameters

BUFFER_SIZE = int(2e6)  # replay buffer size
BATCH_SIZE = 128        # minibatch size
GAMMA = 0.99            # discount factor
TAU = 1e-3              # for soft update of target parameters
LR_ACTOR = 1e-4         # learning rate of the actor 
LR_CRITIC = 1e-4        # learning rate of the critic
WEIGHT_DECAY = 0        # L2 weight decay
UPDATE_EVERY = 20       # frequence to update the network
LEARN_TIMES = 10        # how many times to learn each avtive step


- architecture of neural network
Actor: 
2 layers of 400 and 300 units
batch normalisation between each layers
relu after each layer and tanh for the output function

Critic: 
same architecture as the Actor but without the tanh function

#### process

It was a very iterative process during which I have tried to 
- reduced the parameter space from 2 layers with 400 and 300 units to 128 and 64 units
- add batch normalisation between layers
- tested different replay buffer size by a factor of 10
- tested different the batch size to 128, 64 or 32
- develop the algorithm on one agent, then 20 agents in parallel to speed up the training

## Plot of rewards

![rewards](/image/rewards.png)

## Future work

I would try to solve the environment using  PPO, A3C, and D4PG algorithm to understand the pros and cons of each ones when it comes to distributed training

