# Note on Asynchronous Dynamic Programming

## Some Preliminaries on Policy Improvement, Policy Iteration, and Value Iteration

## Asynchronous Dynamic Programming

A major drawback to the DP methods is that they involve operations over the entire set of the MDP, that is, they require sweeps of the state set. 
If the state set is very large, then even a single sweep can be prohibitively expensive. For example, the game of backgammon has over ${10}^{20}$ states. 
Even if we could perform the value iteration on a million states per second, it would take over a thousand years to complete a single sweep.

_Asynchronous DP_ algorithms are in-place iterative DP algorithms that are not organized in terms of systematic sweels of the state set. 
These algorithms back up the values of states in any order whatsoever, using whatever values of other states happen to be available. 
The values of some states may be backed uo several times before the values of others are backed up once. 
To converge correctly, however, an asynchronous algorithm must continue to backup the values of all the states: it can't ignore any state after some point in the computation. 
Asynchronous DP algorithms allow great flexibility in selecting states to which backup operations are applied. 

For example, one version of asynchronous value iteration backs up the value, in place, of only one state, $s_k$, on each step, $k$, using the value iteration backup. If $0 \leq \gamma \lt 1$, asymptotic convergence to $V^{*}$ is guaranteed given only that all states occur in the sequence $\\{s_k\\}$ an infinite number of times. Note that in the undiscounted episodic case, it is possible that there are some orderings of backups that do not result in convergence, but it is relatively easy to avoid these. Similarly, it is possible to intermix policy evaluation and value iteration backupsto produce a kind of asynchronous truncated policy iteration. Thus, a few different backups from building blocks can be used flexibly in a wide variety of sweepless DP algorithms.

Of course, avoiding sweeps does not necessarily mean that we can get away with less computation. It just means that an algorithm does not need to get locked into a hopelessly long sweep before it can make progress improving a policy. 
