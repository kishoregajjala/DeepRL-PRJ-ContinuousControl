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

For this project, you will work with the [Reacher](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#reacher) environment.

![](reacher.gif)

In this environment, a double-jointed arm can move to target locations. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of your agent is to maintain its position at the target location for as many time steps as possible.

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.

## Distributed Training
For this project, we will provide you with two separate versions of the Unity environment:

* The first version contains a single agent.
* The second version contains 20 identical agents, each with its own copy of the environment.

The second version is useful for algorithms like [PPO](https://arxiv.org/pdf/1707.06347.pdf), [A3C](https://arxiv.org/pdf/1602.01783.pdf), and [D4PG](https://openreview.net/pdf?id=SyZipzbCb) that use multiple (non-interacting, parallel) copies of the same agent to distribute the task of gathering experience.

## Solving the Environment
Note that your project submission need only solve one of the two versions of the environment.

### Option 1: Solve the First Version
The task is episodic, and in order to solve the environment, your agent must get an average score of +30 over 100 consecutive episodes.

### Option 2: Solve the Second Version
The barrier for solving the second version of the environment is slightly different, to take into account the presence of many agents. In particular, your agents must get an average score of +30 (over 100 consecutive episodes, and over all agents). Specifically,

* After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 20 (potentially different) scores. We then take the average of these 20 scores.

* This yields an average score for each episode (where the average is over all 20 agents).
As an example, consider the plot below, where we have plotted the average score (over all 20 agents) obtained with each episode.

The environment is considered solved, when the average (over 100 episodes) of those average scores is at least +30. In the case of the plot above, the environment was solved at episode 63, since the average of the average scores from episodes 64 to 163 (inclusive) was greater than +30.

**I have chosen to solve the first version of the environment with the single agent option using the off-policy DDPG algorithm. The problem was solved using DDPG algorithm where the average reward of +30 over at least 100 episodes was achieved in 230 episodes.**





Follow the instructions below to explore the environment on your own machine! You will also learn how to use the Python API to control your agent.

### Step 1: Clone the DRLND Repository
If you haven't already, please follow the [instructions in the DRLND GitHub repository](https://github.com/udacity/deep-reinforcement-learning#dependencies/ "instructions in the DRLND GitHub repository") to set up your Python environment. These instructions can be found in README.md at the root of the repository. By following these instructions, you will install PyTorch, the ML-Agents toolkit, and a few more Python packages required to complete the project.

(For Windows users) The ML-Agents toolkit supports Windows 10. While it might be possible to run the ML-Agents toolkit using other versions of Windows, it has not been tested on other versions. Furthermore, the ML-Agents toolkit has not been tested on a Windows VM such as Bootcamp or Parallels.

### Step 2: Download the Unity Environment
For this project, you will not need to install Unity - this is because we have already built the environment for you, and you can download it from one of the links below. You need only select the environment that matches your operating system:<br/>

Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux.zip/ "click here")<br/>
Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana.app.zip/ "click here")<br/>
Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86.zip/ "click here")<br/>
Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86_64.zip/ "click here")<br/>

Then, place the file in the p1_navigation/ folder in the DRLND GitHub repository, and unzip (or decompress) the file.

(For Windows users) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64/ "this link") if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

(For AWS) If you'd like to train the agent on AWS ([and have not enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md\ "and have not enabled a virtual screen")), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux_NoVis.zip/ "this link") to obtain the "headless" version of the environment. You will not be able to watch the agent without enabling a virtual screen, but you will be able to train the agent. (To watch the agent, you should follow the instructions to [enable a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md/ "enable a virtual screen"), and then download the environment for the Linux operating system above.)

### Step 3: Explore the Environment
After you have followed the instructions above, open Navigation.ipynb (located in the p1_navigation/ folder in the DRLND GitHub repository) and follow the instructions to learn how to use the Python API to control the agent.

### (Optional) Build your Own Environment

For this project, we have built the Unity environment for you, and you must use the environment files that we have provided.

If you are interested in learning to build your own Unity environments after completing the project, you are encouraged to follow the instructions [here](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Getting-Started-with-Balance-Ball.md/ "here"), which walk you through all of the details of building an environment from a Unity scene.

### How to train a agent
We have two options for training the agent and they are -
1. Directly run the notebook within the online Workspace provided by Udacity Nanodegree for the  Project #1 Navigation.
2. The online workspace does not allow you to see the simulator of the environment; so, if you want to watch the agent while it is training, you should build your own local environment and make necessary adjustments to the path of the Unity environment and train locally.

