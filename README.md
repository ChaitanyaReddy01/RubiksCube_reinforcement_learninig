RubiksCube_reinforcement_learninig


The Rubik’s Cube is a well know combination game, that has tempted the minds of AI researches for a long time. The Rubik’s cube has a large state space with approximately 4.3 × 1019 (43,252,003,274,489,856,000) different states. Out of them only one is the goal state.There are a lot of other solving methods (e.g. Kociemba, Korf, etc.) but, using these techniques would be an interesting approach to solving the Rubik’s cube.

A classic combinatorial puzzle having a big state space and a single goal state is the Rubik's cube. There are special hurdles for machine learning because it is improbable that the goal state can be reached with a series of randomly produced moves.

Rubik's Cube can be solved using pattern-based databases, although these techniques can be memory-intensive and puzzle-specific.

Initially, the cube’s faces are colored in different colors each. We're tackling the Rubik's Cube puzzle using reinforcement learning.

The Rubick's Cube puzzle is a Markov Decision Process in a deterministic episodic context, as seen through the lens of reinforcement learning. The cube represents the state of the environment, all motions are feasible actions, and there are only two possible outcomes: -1 or 1. 

The resolved state is the final state.The project's assumption that a Rubik's cube can only do 180-degree side turns significantly lowers the state space tree of the cube's branching factor.

A reinforcement learning algorithm such as Deep Q-Networks using a simulated Rubik's Cube environment. The algorithm iteratively explores actions and learns optimal strategies to maximize cumulative rewards.


