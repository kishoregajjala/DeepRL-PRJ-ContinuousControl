# DeepRL-PRJ-ContinuousControl

## Project Details

### Project Description
For this project, we will train an agent (robot with double-jointed arm) to move (it’s arm) to target locations.  The goal of the agent is to maintain its position at the target location for as many time steps as possible.

### Reward
A reward of +0.1 is provided for each step that the agent’s hand is in the goal location. 
Observation (State) Space
The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. 

### Action
Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.
The action space is continuous, which allows each agent to execute more complex and precise movements. There's an unlimited range of possible action values to control the robotic arm, whereas the agent with discrete action space was limited to four discrete actions: left, right, forward, backward.

### Project Goal
The goal of the agent is to maintain its position at the target location for as many time steps as possible. The task is episodic, and in order to solve the environment, your agent must get an average score of +30 over 100 consecutive episodes.

## The Environment
The details are taken from the Udacity's Deep Reinforcement Learning Nanodegree program. The environment is based on Unity ML-agents. Please read more about ML-Agents by perusing the GitHub repository.
The project environment provided by Udacity is similar to the Reacher environment on the Unity ML-Agents GitHub page.

The environment contains one brain. I have chosen to solve the first version of the environment with the single agent option using the off-policy DDPG algorithm. The task is episodic, and in order to solve the environment, the agent must get an average score of +30 over 100 consecutive episodes.
