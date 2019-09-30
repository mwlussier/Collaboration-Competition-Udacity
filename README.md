# Collaboration-Competition-Udacity
The objectif of this project is to train agents to bounce a ball over a net without dropping it.
The project environment is provided by Udacity and is similar to, but not identical to the [Unity ML-Agents Tennis](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#tennis).

In this environment, two agents bounce a ball over a net using racket. The goal of each agent is to keep the ball in play. A penalty of -0.01 is given to an agent if it either let the ball hit the ground or hits it when the ball is out of bounds. An agent who hits the ball over the net will receives a reward of +0.1.

The state space has 8 variables corresponding to the position and velocity of the ball and racket. Each agent receives its own, local observation. Two continuous actions are available, corresponding to movement toward, or away from, the net, and jumping.

The task is episodic. In order to solve the environment, the agents must get an average score of +0.5 or more, over 100 consecutive episodes. The score is calculated as the maximum between each agents rewards without discounting it.

------

Follow the instructions below to be able to run the code.

## Step 1: Clone the DRLND Repository
Follow the instructions in the [DRLND GitHub](https://github.com/udacity/deep-reinforcement-learning#dependencies) repository to set up the Python environment. These instructions can be found in **README.md** at the root of the repository. By following these instructions, you will install PyTorch, the ML-Agents toolkit, and a few more Python packages required to complete the project.

## Step 2: Download the Unity Environment
It is not needed to install Unity - you can download the environment provided by Udacity from one of the links below. You only need to select the environment that matches your operating system:

  * Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Linux.zip)
  * Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis.app.zip)
  * Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86.zip)
  * Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86_64.zip)
  
Then, place the file in the _p3_collab-compet/_ folder in the DRLND GitHub repository, and unzip (or decompress) the file.

------
