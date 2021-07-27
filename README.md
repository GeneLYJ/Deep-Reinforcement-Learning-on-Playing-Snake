# Deep-Reinforcement-Learning-on-Playing-Snake

Work inspired by 

higgsfield's repo: https://github.com/higgsfield/RL-Adventure.git

Patrick Loeber's (Python Engineer) repo: https://github.com/python-engineer/snake-ai-pytorch.git

Youtube short demo: https://www.youtube.com/watch?v=bvL2Y8_ai54

Implemented Deep Q Learning on playing Snake for Uni project in 2 weeks.

## Methodology
**A. States**
The dataset of the model are the states in a
Boolean array as a representation of overall of an
image. Figure 1 shows the image consists of 3
categories with 11 states in total:
1. The food (up, down, left or right)
2. The snake last move (forward, left or right)
3. The immediate danger (forward, left or right)


![image](https://user-images.githubusercontent.com/68850993/127124850-34618331-24bf-4180-b5e2-310751016eff.png)


**B. Model**
The following Deep Q-Network (DQN) adopted:
The network receives states and return output
three values - forward, left or right (3 actions).
The last layer uses Softmax function.
The snake game environment is initialised with
epsilon-greedy, 𝜀 = 1 with exploration and
exploitation.
For episode = [1 , M],
For i = [0 , T],
1. Obtain current state (observation space), si
2. Take an action, ai if random generated < 𝜀.
Otherwise, select
ai=maxa Q (si , ai) (1)
3. Execute ai, to the environment and move to
next frame. Obtain next state, si+1.
4. Store transition (si, r, si+1, ai) into the Replay
Buffer, D.
5. If game over, from D, sample random a
minibatch of j transitions. Otherwise, sample
a random transition.
6. Q-value (action) is updated with Bellman’s
equation. Target,
yj = Qnew,j = rj + 𝛾 max􀭟􀱟􀰶􀰭,􀱠Q( si+1,j , ai+1,j ) (2)
if it is not the last transition. Otherwise,
Qnew,j = rj. (3)
7. Compute the loss with Mean Square Error
(MSE). Σ (y􀭨 − 𝑄􀭨(𝑠􀭧, a􀭧 􀭨 ))􀬶
􀬴 (4)
8. Perform backpropagation gradient descent
step on the loss in Step 7 to update the
weights.
In Step 5, Experience Replay from D would help
to smooth out learning distribution and avoid
divergence in the parameters. If the game is not
over, Step 1 to 8 will repeat. Otherwise, exit the
1st for loop after Step 8 to move on next episode.

## Flow Chart
![image](https://user-images.githubusercontent.com/68850993/127125009-29a479bf-74e5-45e2-8c00-dacddfe39f01.png)

