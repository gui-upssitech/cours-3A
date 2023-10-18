Tags: #advanced-ai 

A Markov Decision Process (MDP) is a mathematical framework used to model decision-making in situations where an agent interacts with an environment to achieve a goal. It's a fundamental concept in the fields of artificial intelligence, machine learning, operations research, and reinforcement learning. MDPs are particularly useful for modeling and solving problems involving decision-making under uncertainty.

## Key components 

Here are the key components of a Markov Decision Process. To illustrate, we will be using a famous problem that uses MDP: **Forest Management**.

> [!info] Forest Management
> The considered problem is to manage a forest stand with first the objectiveto maintain an old forest for wildlife and second to make money selling cutwood.

1. **States (S)**:

The set of all possible situations or configurations the system can be in. Each state represents relevant information about the environment that the agent needs to make decisions.

> [!info] States
> Three states are defined, corresponding to 3 age-class of trees: 
> - 0-20 years (state 1)
> - 21-40 years (state 2)
> - more than 40 years (state 3)
> 
> Thestate 3 correspond to the oldest age-class.

2. **Actions (A)**:

The set of all possible actions the agent can take in each state. Actions represent the decisions the agent makes to transition from one state to another.

> [!info] Actions
> **Wait** : the state at the next time period will be min(s+ 1,3) if no fire occured
> **Cut** : the state at the next time period will be 1 (Young forest)

3. **Transition Probabilities (P)**:

The probability distribution of transitioning from one state to another after taking a specific action. It defines the likelihood of moving to a new state given the current state and action.

> [!info] Transition probabilities
> In addition to the actions, there is a probability of $0.1$ that the forest with suffer a wildfire, which resets it to State 1 (Young forest)
>
>For the Wait action
>
| **WAIT**    | Young | Middle Aged | Old |
| ----------- | ----- | ----------- | --- |
| Young       | 0.1   | 0.9         | 0.0 |
| Middle Aged | 0.1   | 0.0         | 0.9 |
| Old         | 0.1   | 0.0         | 0.9 |
> 
> For the Cut action
> 
| **CUT**    | Young | Middle Aged | Old |
| ----------- | ----- | ----------- | --- |
| Young       | 1.0   | 0.0         | 0.0 |
| Middle Aged | 1.0   | 0.0         | 0.0 |
| Old         | 1.0   | 0.0         | 0.0 |

4. **Rewards (R)**:

The immediate rewards received by the agent upon transitioning from one state to another due to a specific action. These rewards are typically numerical values that indicate the immediate benefit or cost associated with the transition.

> [!info] Rewards
> Here are the rewards based on the action taken
> 
> ||Wait|Cut|
> |---|---|---|
> |State 1|0|0|
> |State 2|0|1|
> |State 3|4|2|

5. **Policy (π)**:

A strategy that defines the agent's behavior, specifying which action to take in each state. The policy can be deterministic (a specific action for each state) or stochastic (a probability distribution over actions for each state).

6. **Discount Factor (γ)**:

A discount factor between 0 and 1 that determines the importance of future rewards compared to immediate rewards. It helps in modeling the agent's preference for short-term versus long-term rewards.

> [!info] Recap Graph
> ![[Pasted image 20231018145214.png|500]]
> *Image credit: Julian Trani*

## Usage

The primary objective in an MDP is for the agent to find a policy that maximizes the expected cumulative reward, often referred to as the return. The return is the sum of discounted rewards obtained by following the policy over time.

The agent uses techniques such as [[Policy Iteration]], Value Iteration, Q-learning, and various other reinforcement learning algorithms to find the optimal policy or approximate it in the case of large or continuous state and action spaces.

Markov Decision Processes provide a formal and widely used framework for modeling and solving decision-making problems in a wide range of applications, including robotics, game playing, finance, healthcare, and more.