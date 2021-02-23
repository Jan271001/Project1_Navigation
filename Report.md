# Report

## The result

![Plot of rewards](Navigation_Score.png)

The agent was able to solve the environment in 328 episodes, with an average reward of 13.04. The average reward after all 500 traing-episodes is 15.35.

## The algotithm

For this project I used the standard Deep-Q-Learning-algotithm. I operate with a four layer feed-forward neural network with 37 input nodes, 64 nodes in the two hidden layers and 4 output nodes which represent the four actions the agent can take. The input layer is designed to obtain an input vector with 37 dimensions represanting the current state of the environment. In order to explore the entire state space I used an epsilon greedy policy. To priorize the current reward higher then the expected one of the following timesteps I operate with a discount rate of 0.99. To guarantee the repeatability I applied a random seed of 0.

### Hyperparameters

#### epsilon (temporally variable):

start value: *1.0*

end value: *0.01*

decay: *0.995*

#### discount rate gamma (constant):

value: *0.99*

#### random seed:

value: *0*

### Detailed description of the implementation

For this project I worked with an object-oriented approach. I used three classes called **Agent**, **QNetwork** and **ReplayBuffer** saved in *agent_navigation.py*, *model.py* and *replay_buffer.py*. TAn object of the ReplayBuffer-class represents the memory of the agent, while one of the QNetwork-class could be called the agents brain. The agent in my implementation needs both of them to work properly.

The main file in this repository is the *Navigation_Training.ipynb* notebook. It's the heart of my implementation and hosts the Deep-Q-Learning algorithm. In this file I build the connection with the environment. The environment I operate with is the *Banana.x86_64* from the *Banana_Linux*-folder.  

## Future ideas

The Deep-Q-Learning-algorithm I used in this project accomplished the task described in the README.md-file, but it's far not perfect. To optimize it's performance I'd like to share some possible improvements. On the one hand there are a few enhancements you can do without changing the architecture I work with. In this context adapting the hyperparameters would be a approach with good change of reaching a better performence or a quiker learning. Additional the random seed could be changed to a value != 0 (For example 1 or the current time). This will lead to a different initial network with every start of the trainings process. Letting the agent train many times with completly different neural networks will help to avoid local minima in the error-function and lead to a better chance of finding the optimal policy. Of course it's also feasible to set a higher number of training episodes (well-considerd the simplest adaption). On the other hand, the network architecture could be changed or another type of algorithm could be used. This fittings are more complex and need more knowledge about AI, nonetheless they could lead to a massiv improvement in the performance of the agent. As example I'd like to menttion a bigger net with more hidden layers or the application of the Dobble-Q-Learning-algotithm.   
