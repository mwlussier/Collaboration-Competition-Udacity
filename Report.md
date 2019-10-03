## Collaboration and Competition Project

To resolve the project, a **Multi Agent Deep Deterministic Policy Gradient** (MADDPG) was used.

DDPG is an off policy actor-critic algorithm that uses the concept of target networks. MADDPG is a centralized training and decentralized execution algorithm that can be used in either cooperative, competitive, and mixed scenarios.

During training, the critic for each agent uses extra information like state's observed and actions taken by all the other agents.
During execution, each actor has only access to its agent observation and actions, which mean that they produced different reward structure.

To makes the model exploration process more robust, a noise function (Ornstein-Uhlenbeck process) is added to the MADDPG agent during the action stage.

Furthermore, a soft update function is applied to both the actor and critic network during their learning stage. This function blends a very small portion of the local network, which is the most up to date one, with the target network, which is the one we use for prediction to stabilize training.

The model architecture include for both actor and critic networks, three (3) fully connected layers and one (1) batch normalization layer between the first and the second layer. We are using a ReLu activation function for the two (2) first fully connected layers and a tangent function for the last one (only in the Actor network).

The batch normalization is used to apply a normalization process to the outputs of a previous layer such as it's done during the preprocessing phase of the initial data. This should increase the stability of the network and accelerate the learning process. Batch normalization is used with its default variables.

## Result
The training was stopped if the average score was higher than 0.5 and the number of episodes was higher than 1500 or if the average score was higher than 1.5.
The best model achieved an average score of 1.51 after 864 episodes of training. It achieved an average score of 0.50 or more between the 800 and 861 episode. The hyperparameters used are as follow:

* BUFFER_SIZE:       1e6
* BATCH_SIZE:        128
* GAMMA:             0.99
* TAU:               1e-3
* LR_ACTOR:          1e-5
* LR_CRITIC:         1e-4
* WEIGHT_DECAY:      0
* THETA:             0.15
* SIGMA:             0.10
* UPDATE_FREQUENCY:  3

For both Actor and Critic network:
* FC1_UNITS:         128
* FC2_UNITS:         256


## Experimentation
It must be specified that for both actor and critic network, only the fully connected layers size as been changed and that the batch size match the first fully conneccted layer size:
(BATCH_SIZE, FC1_UNITS, FC2_UNITS)


1. (128, 128, 128)

![alt text](https://github.com/mwlussier/Collaboration-Competition-Udacity/blob/master/images/collab_comp_128_128_128.png)

2. (128, 128, 256)

![alt text](https://github.com/mwlussier/Collaboration-Competition-Udacity/blob/master/images/collab_comp_128_128_256.png)

3. (256, 256, 256)

![alt text](https://github.com/mwlussier/Collaboration-Competition-Udacity/blob/master/images/collab_comp_256_256_256.PNG)

4. (256, 256, 128)

![alt text](https://github.com/mwlussier/Collaboration-Competition-Udacity/blob/master/images/collab_comp_256_256_128.png)

## Future Work
* The natural amelioration would be to complexify the network architecture by adding more hidden layers to both actor and critic networks. Further exploration in the others hyperparameters such as the Sigma variable in the noise function could help increase the performance and add robustness to the model.
* An interesting implementation would be to resolve this environment using Monte Carlo Tree Search (MCTS) in continuous action space [1].

[1] [http://liacs.leidenuniv.nl/~plaata1/papers/pal2018.pdf](http://liacs.leidenuniv.nl/~plaata1/papers/pal2018.pdf)
