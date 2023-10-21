
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

s,a -> s'

This is stochastic, so we can add probability P to the transition:

P(s' | a,s)

There is a reward associated with s,a,s' construct:

s,a,s',r 

Taking action a in state s -> leads to state s' and a reward

The reward is a function on the (s,a,s') construct:

R(s,a,s')

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