
"Games are interesting because they're too hard to solve." - Russell and Norvig

Hans Moravec Paradox

Things that humans find hard: no problem!
Things that humans find easy: not so much

Leads to the trend of generalization in game playing AI

DQN - DeepMind agent

The DQN agent can learn to play Atari video games

Reinforcement learning is:
- how agents can learn what to do in the absence of labeled examples of what to do 
- "Imagine playing a new game whose rules you don't know; after a hundred or so moves, your opponent announces 'You lose' This is reinforcement learning in a nutshell."

State: screen pixels
Actions: L (left), R (right), NOWT (nothing)
Rewards: score, done


How can we create an Ai that can play games?
- most games involve an iterated process of observing and acting.
- most games involve some sort of positive or negative result.

Breakout:

Observation --> Pixels on the screen
Actions --> Moving left, right or standing still
Rewards --> Break disappearing, get a point, ball goes out of screen

Formalization

The player observes state s
the player takes action a
the player observer the next state s'

s, a -> s'

This is stochastic, so we can add probability P to the transition:

P(s' | a, s)

There is a reward associated with s, a, s' construct:

s, a, s', r 

Taking action a in state s -> leads to state s' and a reward

The reward is a function on the (s, a, s') construct:

R(s, a, s')

Those two elements combined result in a Markov Decision Process which is a way to formalize a stochastic sequential decision problem:

P(s' | a,s) --> State transitions

R(s,a,s') --> Reward function

The action policy tells us what to do in a given state.

Policies are denoted with $\pi$

$\pi$(s) -> a

The policy for state s is to take action a


This is a sequential decision problem, not one shot. Reward might come in the far future.

An optimal policy maximizes reward over a sequence of actions

So the action you take now should unlock maximum potential rewards going into the future

The Bellman equation 

Bellman equation defining the value of a given action in a given state based on future reward

The state transition matrix tells us how the state will
change over time based on our chosen actions
The action policy dictates what the chosen actions will be
in each state. It involves choosing the highest value action
The problem is we need to know the complete transition
matrix and the associated rewards to make an action
policy – not easy for Atari games!


States are the pixels on the screen – too many
possible combinations
Also, how to know what the possible combinations
actually are?
And most states have zero reward

The answer to the incomplete MDP data is to
approximate the value function – that
approximation is the Q function
Q-learning involves learning the best Q-
function that we can: Q*

And so in essence, before we look at the details on that slide, what Q-learning

is doing is it's saying, well I'm not going to have a perfect value function.

I don't worry about that, but I'm going to try and

get my best approximation of what the value function is.

So I'm going to somehow through observation,

learn what the value function is.

Okay, so the Q function in Q and

the Q function is an approximation of the value function.


Great attempt! The Bellman equation says that the value (reward going into the future) of a given action, in a given state, is based on the reward that we might achieve in the future assuming that we are taking a certain decision policy. The issue with the Breakout game is that we do not know the complete transition matrix and the associated rewards to make an action policy.

## Agent architecture

An agent is an entity that can observe and act autonomously.

The agent architecture must solve two problems:
- No state transition matrix
- No action policy

![[Pasted image 20231021185633.png]]

The agent on the left and the game simulation on the right.

The agent:
- makes observations about states and rewards.
- acts on the world by taking actions.

Within the agent we have a replay buffer used to gather observations about states, actions, the nest state was, the reward and whether the game was done or not.

The Q function is the DNN which is given a state and will output the action that needs to be taken. 

The behavior is going to be to collect observations. then periodically it is going to stop collecting observations and train the Q function on the current set of observations.

Epsilon greedy exploration 

From random to using Q function.
It has another block called Random, at the beginning it will use that block instead of the Q function to gather data to then train the Q function.

Epsilon greedy means how greedy you are going to be over time and use the Q function. At first the greed is going to be 0 and data is going to be gathered only through the Random block.

After some training, we are going to increase the greed so that the agent will choose actions randomly, but occasionally it is going to use the Q function. As greed goes up, it is going to use the Q function more and more.

## Loss function

The loss function, it tells us what is the difference between what we've produced, and what we're expecting to produce.

The proxy is the previous version of the network before we do the training.
One is used to estimate the value of something and the other one we train over time.

Equation explanation: 
Thetas are the weights in the networks.
The loss of the current network is the result of the equation.
We take a random sample (uniform random sample) from the replay buffer D to yield a set of states, actions, rewards and next states.

Estimation of the output using the old network, the proxy network. We ask this old network for what the values is going to be + the known reword. Best guess + known reward 

Minus the answers the current network yields.

Great attempt! Since we do not know exactly what the correct answer is for the network, the trick is to take an older version of the network, add to it the correct reward signal found in the replay buffer, and compare it with what the current network generates. Overtime, this process will improve the network performance.

### Visual processing

The state is actually three frames.

This expression is used to decide which moves an AI should take when it is playing a video game. s is the state, which is what is on the screen or the last few screens of the game. a is the action, which can be move left, move right etc. The expression evaluates the actions in terms of their potential future rewards (r). Rewards are points gained in the game, e.g. shooting an alien in Space Invaders. t is the time, so t+1 is one step in the future. ππ is a bit complicated but that part is saying 'assuming the AI makes the highest value decisions going into the future'.

## Gym

- A way of providing standardized environments for reinforcement learning algorithms to operate in.
- Allows the developer to focus on their agent instead of the simulation.
- Includes version standard set of environments, enabling easy comparison.


