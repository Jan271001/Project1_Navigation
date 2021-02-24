# Report

## The result

![Plot of rewards](Navigation_Score.png)

The agent was able to solve the environment in 328 episodes, with an average reward of 13.04. The average reward after all 500 training-episodes is 15.35.

## The algorithm

For this project I used the standard Deep-Q-Learning-algorithm. I operate with a four layer feed-forward neural network with 37 input nodes, 64 nodes in the two hidden layers and 4 output nodes which represent the four actions the agent can take. The input layer is designed to obtain an input vector with 37 dimensions representing the current state of the environment. In order to explore the entire state space I used an epsilon greedy policy. To prioritize the current reward higher then the expected one of the following time steps I operate with a discount rate of 0.99. To guarantee the repeatability I applied a random seed of 0.

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

For this project I worked with an object-oriented approach. I used three classes called **Agent**, **QNetwork** and **ReplayBuffer** saved in *agent_navigation.py*, *model.py* and *replay_buffer.py*. An object of the ReplayBuffer-class represents the memory of the agent, while one of the QNetwork-class substitute for the agents brain. The agent in my implementation needs both of them to work properly. As a consequence, both classes get imported in the *agent_navigation.py*-file.

The main file in this repository is the *Navigation_Training.ipynb* notebook. It's the heart of my implementation and hosts the Deep-Q-Learning algorithm. In this file I establish the connection with the environment. The environment I operate with is the *Banana.x86_64*-environment. It's saved in the *Banana_Linux*-folder. At first I had to integrate the different libraries and classes, including the Agent-class. In the next step I defined the different hyperparameters like mentioned  in the chapter above. Additional I set the number of max time-steps (e.g. 1000) and max episodes (e.g. 500) and save the environment parameters like state- and action-space (e.g. 37/4). In the following lines I load the environment and define an agent as well as the training-method **def_train(...)**.

Def_train() operates with the already mentioned Deep-Q-Learning-algorithm. Before I address the actual Q-learning I have to define the saving of scores as well as the reset of the environment. That relocated environment depict the first state the agent observes in each episode. It gets repositioned prior every episode. The actual algorithm has the following structure:

#### Pseudocode:

*open loop(max time steps like defined above)*

*select an action*

*send the action to the environment*

*get the next state*
            
*get the reward*
            
*see if episode has finished*

*save step in memory and learn from this step*

*update the score*

*roll over the state to next time step*

*exit loop if episode finished*

This pseudocode represents the proceed of one single episode. It gets repeated till the number of max episodes is reached. After that, there's only a few things left. A plot of the score and a line code to close the environment.

As a last important file in this notebook I wrote an implementation showing the performance of an already trained agent (*Navigation_Trained_Agent_Test.ipynb*). 

## Future ideas

The Deep-Q-Learning-algorithm I used in this project accomplished the task described in the README.md-file, but it's far not perfect. To optimize it's performance I'd like to share some possible improvements. On the one hand there are a few enhancements you can do without changing the architecture I work with. In this context adapting the hyperparameters would be a approach with good change of reaching a better performance or a quicker learning. Additional the random seed could be changed to a value != 0 (For example 1 or the current time). This will lead to a different initial network with every start of the trainings process. Letting the agent train many times with completely different neural networks will help to avoid local minima in the error-function and lead to a better chance of finding the optimal policy. Of course it's also feasible to set a higher number of training episodes (well-considerd the simplest adaption). On the other hand, the network architecture could be changed or another type of algorithm could be used. These fittings are more complex and need more knowledge about AI, nonetheless they could lead to a massive improvement in the performance of the agent. As an example I'd like to mention a bigger neural network including more hidden layers, or the application of the Double-Q-Learning-algotithm.   
