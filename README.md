# Project1_Navigation
The first project in the udacity deep-reinforcement-learning nanodegree

Note: This repository is created for Linux ubuntu 20.04. It's only guaranteed to work on this version. Nonetheless it should work on other Linux versions as well.

## The Task
This GitHub repository is designed to solve an environment similar (but not identical!) to the Unity-Banana-Collector environment.

## The Environment
The agent in this repository is designed to navigate and collect bananas in a large square world. A reward of +1 is provided for collecting a yellow banana, and a 
reward of -1 is provided for collecting a blue banana. Thus, the goal of the agent is to collect as many yellow bananas as possible while avoiding blue bananas. 
The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around the agent's forward direction. Given this 
information, the agent learned how to best select actions. Four discrete actions are available, corresponding to

*0 = move forward.*

*1 = move backward.*

*2 = turn left.*

*3 = turn right.*

The task is episodic, and in order to solve the environment, the agent must reach an average score of +13 over 100 consecutive episodes.

## Getting started
Before running the code in the jupyter-notebook make sure to install the necessary libraries. If you'd like to install them on your own machine please follow the instructions below. These instructions imply that your machine already satisfy conditions to run all, not explicitly for this project necessary, requirements like for example jupyter notebooks or python3-code.

To set up your python environment making the code in this repository run, follow the instructions in this repository: https://github.com/udacity/deep-reinforcement-learning#dependencies.

## Use the Code
In order to use the code in this repository make sure your machine satisfy  all requirements in the "Getting started"- paragraph above. Now you are free to clone this repository and use it on your own computer(**!No GPU-support needed!**). After cloning, you have to open a terminal and navigate to the folder representing the repository. Please open a jupyter notebook using the *jupyter notebook* command. The Notebook will open in your browser. Thereafter you have to open the *Navigation_Training.ipynd*-file and restart the kernel by clicking on the "restart"-button. A dialogue will open, please click on the "restart and run all cells"-button. Finally you can watch the agent train. If you prefer watching an already trained agent, please open the *Navigation_Trained_Agent_Test.ipynd*-file.

**For additional information please read the "Report.md"-file**
