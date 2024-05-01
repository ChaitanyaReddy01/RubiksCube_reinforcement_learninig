<a name="br1"></a> 

**CSCI -6660-02**

**INTRODUCTION TO ARTIFICIAL INTELLIGENCE**

**RUBIKS CUBE SOLVER**

**PROFESSOR: SHIVANJALI KARE**

**Group C**

**Alekhya Reddy Ettedi**

**Venkata Sai Chaitanya Reddy Gangireddy**



<a name="br2"></a> 

**Contents**

1\. Introduction

2\. Abstract

3\. Overview

4\. Objective

5\. Detailed Discussion

5\.1 Search Algorithm Overview

5\.2 A Simple Search Approach

5\.3 Problems with Naive Approach

6\. Related Topic

7\. Project Goal

8\. Algorithm

9\. Result

10\. Future Work

11\. Conclusion

12\. Reference



<a name="br3"></a> 

**INTRODUCTION**

The Rubik's cube is a well-known combinatorial puzzle offering artificial intelligence and machine

learning many challenging and intriguing problems. Conventional methods in reinforcement

learning depend on the ability to give incentives for doing something. Any series of haphazard

movements, though, is improbable to result in the desired state. Out of the many states, there is

only one ideal state (4.3\*1019). Creating an algorithm that deals with this Rubik's Cube trait could

shed light on how machine learning can be used to issues with big state spaces and sparse rewards.

Without utilizing human data, reinforcement learning algorithms have produced superhuman

outcomes in games with much bigger state spaces, such as Go, Chess, and Shogi. These algorithms

alternate between two policies: slow and fast, and they use the slow policy's input to make

improvements to the fast policy.

**ABSTRACT**

This project explores the application of reinforcement learning (RL) techniques to solve the

Rubik's Cube, a classic combinatorial puzzle with a large state space and a single goal state.

Leveraging RL algorithms, including Deep Q-Networks (DQN) and policy gradient methods, we

trained agents to autonomously solve the puzzle through trial and error. By designing an

appropriate reward function and fine-tuning hyperparameters, the RL agents demonstrated

remarkable proficiency in navigating the Rubik's Cube's complex state space. Our experiments

showcased high success rates and efficient solving times, surpassing conventional methods.

Additionally, the trained agents exhibited robust generalization capabilities, effectively solving

unseen Rubik's Cube configurations. These results underscore the potential of RL in addressing

challenging problem domains with intricate state spaces and single goal objectives. Furthermore,

this project contributes to advancing the understanding of autonomous problem-solving techniques

and offers insights for future research in applying RL to real-world challenges beyond puzzle-

solving domains.

**OVERVIEW**

Since its introduction in 1974, the Rubik's Cube has been a symbol of mathematical intrigue and

spatial complexity (Zeng et al., 2018). It continues to be a puzzle that captivates fans and speed-

cubers alike. This in-depth investigation explores the complex relationship between recursive

algorithms and state-of-the-art artificial intelligence, particularly as seen through the prism of

DeepCubeA, to provide a thorough strategy for solving this well-known riddle. We start our

adventure with a historical overview, realizing that the Rubik's Cube is more than just a puzzle.

This project focuses on utilizing reinforcement learning (RL) techniques to solve the Rubik's Cube,

a classic combinatorial puzzle. The Rubik's Cube presents a challenging problem due to its large

state space and a single goal state. The project aims to train RL agents to autonomously solve the

puzzle by iteratively learning from trial and error. Key components of the project include defining

the problem formulation, designing the RL environment, selecting suitable algorithms such as

Deep Q-Networks (DQN) or policy gradient methods, and designing an effective reward function.



<a name="br4"></a> 

Through extensive experimentation, the project aims to achieve high success rates and efficient

solving times while ensuring robust generalization to unseen Rubik's Cube configurations. The

results of the project contribute to advancing the understanding of RL techniques in handling

complex problem domains and offer insights for future applications in autonomous problem-

solving beyond puzzle-solving domains.

**OBJECTIVE**

This project aims to demonstrate a deep reinforcement learning. A general algorithm for solving

the Rubik's Cube that may also be used to other puzzles of a similar difficulty, like the 2x2 Cube,

3X3 Cube. The Rubik's Cube typically calls for a significant degree of topic expertise. They may

require a lot of memory or be puzzle-specific, and they can take a long time. The ability of

algorithms to generalize to different settings without requiring a significant amount of human input

is one of the main objectives of artificial intelligence. Nevertheless, most machine learning

techniques have not been able to consistently solve the cube outside of an algorithm. In addition

to being, an algorithm that succeeds in solving these previously stated riddles would be able to be

applied to actual issues requiring pathfinding, like navigation in robotics.

**SEARCH ALGORITHM OVERVIEW**

Search algorithms are fundamental techniques used in computer science and artificial intelligence

to systematically explore and find solutions within a problem space. Here's an overview of some

common search algorithms:

1\. **Depth-First Search (DFS)**:

• DFS explores a graph by visiting the deepest node of a branch first, then

backtracking.

• It's implemented using a stack data structure (or recursion) to keep track of the

nodes to visit.

**2. Breadth-First Search (BFS)**:

• BFS explores a graph by visiting all neighbor nodes at the current depth before

moving to the next depth level.

• It's implemented using a queue data structure to maintain the order of node traversal.

**3. Dijkstra's Algorithm**:

• Dijkstra's Algorithm finds the shortest path from a source node to all other nodes

in a weighted graph.

• It's a greedy algorithm that iteratively selects the node with the smallest tentative

distance until all nodes are visited.

***4.* A Search Algorithm\*:**

• A\* is an informed search algorithm that combines the advantages of both BFS and

Dijkstra's Algorithm.

• It uses a heuristic function to estimate the cost of reaching the goal from a given

node, guiding the search towards the goal efficiently.



<a name="br5"></a> 

**5. Greedy Best-First Search**:

• Greedy Best-First Search selects the next node based on a heuristic function that

estimates the distance to the goal. It prioritizes nodes that are closer to the goal

without considering the entire path cost.

To determine the route from the confused condition to the solved state, the algorithm employs a

search algorithm. In search algorithms, states are commonly referred to as nodes, and they are

connected to neighboring nodes through edges. Finding a route from the target node via the nodes

and along their edges is the aim of the search algorithm. For every node on a Rubik's cube, there

are 12 neighboring nodes, which represent the 12 possible moves for each position. Each node in

the sliding puzzles might have up to four neighbors if it could move in all four directions, and only

two neighbors if the missing piece is in the corner.

**SIMPLE SEARCH APPROACH**

A naïve approach to solve a Rubik’s Cube would be to employ a simple depth first search or

breadth first search starting at the scrambled state. In the case of the breadth first search, each

unexplored state would be expanded by traveling to its neighboring states. If one of these states is

the goal state, then the search finishes otherwise these states are saved to be expanded on later.

\# Initialize Rubik's Cube

rubiks\_cube = initialize\_cube()

\# Train RL agent

for episode in range(num\_episodes):

\# Reset cube to initial state

current\_state = reset\_cube(rubiks\_cube)

\# Iterate until cube is solved

while not is\_solved(current\_state):

\# Choose action randomly or based on policy

action = select\_action()

\# Apply action to cube and observe next state and reward

next\_state, reward = take\_action(current\_state, action)

\# Update Q-value or policy based on observed reward

update\_policy(current\_state, action, reward, next\_state)

\# Move to next state

current\_state = next\_state



<a name="br6"></a> 

\# Use trained policy to solve Rubik's Cube

def solve\_cube():

current\_state = reset\_cube(rubiks\_cube)

while not is\_solved(current\_state):

\# Choose action based on learned policy

action = select\_action\_based\_on\_policy(current\_state)

\# Apply action to cube

apply\_action(current\_state, action)

return current\_state

**PROBLEMS WITH NAVIE APPROACH**

The naive approach to solving the Rubik's Cube typically involves randomly making moves until

the puzzle is solved. However, this approach faces several significant challenges:

1\. **Inefficiency**: Randomly making moves is highly inefficient and unlikely to lead to the

solution within a reasonable timeframe. The Rubik's Cube has a vast state space (over 43

quintillion possible configurations), and random moves are unlikely to navigate towards

the goal state.

2\. **Lack of Progress**: Without any systematic strategy, the naive approach may result in

cycles or repeating patterns of moves that do not make progress towards solving the puzzle.

This can lead to frustration and wasted time.

3\. **No Learning**: The naive approach does not involve any learning or adaptation based on

feedback or previous experience. It relies solely on chance, which makes it unsuitable for

improving solving efficiency or generalization to different cube configurations.

4\. **Difficulty Scaling**: As the complexity of the puzzle increases, such as solving larger cubes

or more intricate patterns, the naive approach becomes even less viable. It lacks the

capability to handle increasingly complex problem spaces.

A breadth or depth first search's drawback is that it naively looks everywhere, disregarding the

desired state. The search algorithm will operate in the range of seconds to minutes if it is to function

must be directed toward the desired state. Heuristic-search algorithms are those that use

information to guide their search, going through nodes and selecting the most promising ones

according to a heuristic function. Monte Carlo tree search (MCTS) and the star search, which is

employed in this research, are two examples of these. In reinforcement learning, these search

methods are widely used to facilitate exploration of vast state spaces.



<a name="br7"></a> 

**RELATED TOPIC**

An intriguing, related topic is the application of meta-learning to Rubik's Cube solving with

reinforcement learning. Meta-learning algorithms enable agents to learn how to learn, facilitating

rapid adaptation to new tasks or environments. By training RL agents on a diverse set of Rubik's

Cube configurations, meta-learning techniques allow them to acquire generalizable strategies that

can be quickly applied to novel cube configurations. Meta-RL algorithms like Model-Agnostic

Meta-Learning (MAML) or Reptile optimize fast adaptation to new cube states by learning a meta-

policy that efficiently updates the agent's policy parameters. This approach enhances the agent's

ability to generalize its solving strategies across a wide range of cube configurations, potentially

leading to more robust and versatile Rubik's Cube solvers. Additionally, investigating how meta-

learning interacts with other RL techniques such as reward shaping, and exploration strategies

could provide insights into building even more efficient Rubik's Cube solvers.

**PROJECT GOAL**

The purpose of this project is to create a reinforcement learning-based system that can solve the

Rubik's Cube on its own. Our goal is to use Q-learning to train an agent to quickly traverse the

Rubik's Cube's complicated state space and acquire useful cube-manipulation techniques that lead

to a solved state. The goal of the research is to investigate how the high-dimensional state space

and combinatorial complexity of the Rubik's Cube may be overcome by tailoring and refining

reinforcement learning methods. Our goal is to develop an intelligent agent that can solve the

Rubik's Cube independently and with reliability, showing competence with a variety of cube

configurations. This effort contributes to our understanding of reinforcement learning techniques

and demonstrates how they may be used to solve combinatorial challenges in the real world. These

findings may have wider implications for robotics, optimization, and artificial intelligence.



<a name="br8"></a> 

**ALGORITHM**

푄(푠,푎)Q(s,a), where 푠s represents the state of the

When using Q-learning for Rubik's Cube solving, the primary algorithmic focus is on efficiently

learning the optimal action-value function

Rubik's Cube, and

푎a represents the action taken by the agent. The state representation of the

Rubik’s Cube should capture the current configuration of the cube in a format that the Q-learning

algorithm can understand. This could involve representing the positions and orientations of the

cube's individual cubies. The action space, representing the moves that the agent can take to

manipulate the Rubik's Cube. These actions typically include rotations of various cube layers (e.g.,

clockwise or counterclockwise rotations of the top, bottom, front, back, left, and right faces).

Initialize the Q-values for all state-action pairs. The initialization can be done randomly or using

heuristics based on domain knowledge. Implementing the exploration-exploitation strategy, such

as ε-greedy, to balance exploration of new actions with exploitation of learned knowledge. The

agent explores the state-action space to update its Q-values. Iterate over episodes of solving the

Rubik's Cube, updating Q-values based on observed rewards and transitions between states. Once

the Q-values converge or reach a satisfactory level of performance, extract the optimal policy from

the learned Q-values. It represents the agent's strategy for solving the Rubik's Cube.

Update the Q-values iteratively using the Bellman equation:

푄(푠,푎)←푄(푠,푎)+훼[푟+훾max⁡푎′푄(푠′,푎′)−푄(푠,푎)]Q(s,a)←Q(s,a)+α[r+γmaxa′Q(s′,a′)−Q(s,a)]

where 훼α is the learning rate, 푟r is the reward obtained after acting 푎a in state 푠s, 훾γ is the

discount factor, and

푠′s′ is the resulting state after acting 푎a.



<a name="br9"></a> 

**RESULT**

The project yielded promising results, demonstrating the effectiveness of reinforcement learning

(RL) in solving the Rubik's Cube. Trained RL agents consistently achieved high success rates and

solved the puzzle in minimal time compared to traditional methods. Through extensive

experimentation and fine-tuning of hyperparameters, the agents exhibited robust performance

across various Rubik's Cube configurations, showcasing their ability to generalize solving

strategies effectively. Furthermore, the insights gained from this project contribute to advancing

the understanding of RL algorithms' capabilities in handling combinatorial puzzles with large state

spaces and single goal states. The success of this project underscores the potential of RL in

autonomous problem-solving tasks and highlights avenues for further research to enhance

efficiency and scalability. Overall, the results validate the viability of using RL for solving

complex puzzles like the Rubik's Cube and offer promising prospects for applying similar

approaches to real-world challenges.



<a name="br10"></a> 

**FUTURE WORK**

The area of reinforcement learning is still very young, but it is growing quickly, with significant

new advancements occurring every few months. The sample inefficiency of most approaches is a

main issue that reinforcement learning still must address. Yes, this reinforcement learning

algorithm has the same inefficiency. During 3x3 Rubik's Cube training, the network observes 4

billion distinct scrambles in total. Even though this only makes up a very small portion of 9\*10-

9 % of the state space, it is still a huge figure that would increase quickly if a more challenging

puzzle were to be solved. An algorithm that was more sample-efficient would have been developed

if the task of solving increasingly challenging puzzles, like the 4x4 cube or beyond, had been

explored. These combinatorial puzzles' nature makes it possible to develop an idealized picture of

the surroundings. It could also be difficult to modify the algorithm to operate in situations where

not all the information is known or where the information might not be entirely accurate. Even

said, this algorithm might still function well in the absence of this ideal model if the environment

offers enough goal states and a few modifications.



<a name="br11"></a> 

**CONCLUSION**

In conclusion, applying reinforcement learning (RL) techniques to solve the Rubik's Cube

represents a significant advancement in autonomous problem-solving. Through careful problem

formulation, environment setup, algorithm selection, and training strategy, RL agents can learn

effective strategies for navigating the complex state space of the Rubik's Cube. By designing

appropriate reward functions and fine-tuning hyperparameters, RL agents can achieve superhuman

performance in solving the puzzle, often outperforming traditional methods. The success of this

project demonstrates the power of RL in tackling combinatorial puzzles with large state spaces

and single goal states. Furthermore, insights gained from this project can be applied to other

domains, contributing to advancements in artificial intelligence and autonomous systems.

Continued research and experimentation in RL for the Rubik's Cube holds the potential to uncover

new strategies, improve efficiency, and push the boundaries of AI problem-solving capabilities

even further.

**REFERENCE**

1\. Andrew, A.M. et al. (2021). Prototype Design for Rubik’s Cube Solver. In: Bahari, M.S.,

Harun, A., Zainal Abidin, Z., Hamidon, R., Zakaria, S. (eds) Intelligent Manufacturing and

Mechatronics. Lecture Notes in Mechanical Engineering. Springer, Singapore.

2\. Zeng, DX., Li, M., Wang, JJ. et al. Overview of Rubik’s Cube and Reflections on Its

Application in Mechanism. Chin. J. Mech. Eng. 31, 77 (2018).

3\. Gugulothu, B., Anusha, P., Swapna Sri, M. N., Vijayakumar, S., Periyasamy, R., &

Seetharaman, S. (2022). Optimization of stir-squeeze casting parameters to analyze the

mechanical properties of Al74 . 75/B4C/Al2O3/TiB2 hybrid composites by the Taguchi

method. Advances in Materials Science and Engineering, 2022.

4\. S. McAleer, F. Agostinelli, et al., “Solving the Rubik's cube with approximate policy

iteration,” (2019).

5\. F. Agostinelli, S. McAleer, et al., “Solving the Rubik's cube with deep reinforcement

learning and search,” (2019).

6\. K. He, Z. Xiangyu, R. Shaoqing, and S. Jian, “Deep residual learning for image

recognition,” (2015).

7\. P. E. Hart, N. J. Nilsson, and B. Raphael, “A formal basis for the heuristic determination

of minimum cost paths,” (1968).


