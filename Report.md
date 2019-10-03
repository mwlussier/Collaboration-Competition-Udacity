## Reacher Project

To resolve the project, a **Multi Agent Deep Deterministic Policy Gradient** (MADDPG) was used.

DDPG is an off policy actor-critic algorithm that uses the concept of target networks. MADDPG is a centralized training and decentralized execution algorithm that can be used in either cooperative, competitive, and mixed scenarios.

During training, the critic for each agent uses extra information like state's observed and actions taken by all the other agents.
During execution, each actor has only access to its agent observation and actions, which mean that they produced different reward structure.

To makes the model exploration process more robust, a noise function (Ornstein-Uhlenbeck process) is added to the MADDPG agent during the action stage.

Furthermore, a soft update function is applied to both the actor and critic network during their learning stage. This function blends a very small portion of the local network, which is the most up to date one, with the target network, which is the one we use for prediction to stabilize training.

The model architecture include for both actor and critic networks, three (3) fully connected layers and one (1) batch normalization layer between the first and the second layer. We are using a ReLu activation function for the two (2) first fully connected layers and a tangent function for the last one (only in the Actor network).

The batch normalization is used to apply a normalization process to the outputs of a previous layer such as it's done during the preprocessing phase of the initial data. This should increase the stability of the network and accelerate the learning process. Batch normalization is used with its default variables.

## Result
The best model achieved an average score of xxx after xxx episodes of training. It achieved an average score of 0.50 or more at best 1500 episodes. The hyperparameters used are as follow:

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


It seem, for this environment, that as we raise our network complexity, we reduce the number of episode needed to reach our goal.
It must be specified that for both actor and critic network, only the fully connected layers size as been changed and that the batch size match the first fully conneccted layer size:
(BATCH_SIZE, FC1_UNITS, FC2_UNITS)


(128, 128, 128)

(128, 128, 256)

(256, 256, 256)

(256, 256, 128)


## Future Work
* The natural amelioration would be to complexify the network architecture by adding mor hidden layers to both actor and critic networks. 
* An interesting implementation would be to resolve this environment using Monte Carlo Tree Search (MCTS) in continuous action space [1].

[1] [http://liacs.leidenuniv.nl/~plaata1/papers/pal2018.pdf](http://liacs.leidenuniv.nl/~plaata1/papers/pal2018.pdf)
