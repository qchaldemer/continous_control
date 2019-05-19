# Actor-Critic Methods

## Environment details
In this environment, a double-jointed arm can move to target locations. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of your agent is to maintain its position at the target location for as many time steps as possible.

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.

The environment is considered solved, when the average (over 100 episodes) of those average scores is at least +30.

### Download the Unity Environment

Version 2: Twenty (20) Agents
Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher.app.zip)
Windows (64-bit): [https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86_64.zip)

## Instructions
- Open `Continuous_Control.ipynb` to train the DDPG agent
- `model.py` contains the NN for the actor and critics
- `ddpg_agent.py` contains the implementation of DDPG agent
- `checkpoint_actor.pth` & `checkpoint_critic.pth` contains the weights of the trained agent

Refer to `report.md` for implementation details of the algorithm