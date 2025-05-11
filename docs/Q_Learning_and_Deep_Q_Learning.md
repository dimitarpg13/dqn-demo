# Q-Learning and Deep Q-Learning

## Q-Learning

Q-Learning is a form of model-free reinforcement learning. It can also can be viewed as a method of asynchronous dynamic programming. 



## Asynchronous Dynamic Programming

A major drawback to the DP methods is that they involve operations over the entire set of the MDP, that is, they require sweeps of the state set. If the state set is very large, then even a single sweep can be prohibitively expensive. For example, the game of backgammon has over ${10}^{20}$ states.  Even if we could perform the value iteration on a million states per second, it would take over a thousand years to complete a single sweep.

_Asynchronous DP_ algorithms are in-place iterative DP algorithms that are not organized in terms of systematic sweels of the state set. These algorithms back up the values of states in any order whatsoever, using whatever values of other states happen to be available. The values of some states may be backed uo several times before the values of others are backed up once. To converge correctly, however, an asynchronous algorithm must continue to backup the values of all the states: it can't ignore any state after some point in the computation. Asynchronous DP algorithms allow great flexibility in selecting states to which backup operations are applied. 

