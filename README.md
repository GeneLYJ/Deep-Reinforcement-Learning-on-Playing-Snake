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

![image](https://user-images.githubusercontent.com/68850993/127125253-abefbfa8-5922-4c03-848e-82f5012c36ed.png)

In Step 5, Experience Replay from D would help
to smooth out learning distribution and avoid
divergence in the parameters. If the game is not
over, Step 1 to 8 will repeat. Otherwise, exit the
1st for loop after Step 8 to move on next episode.

## Flow Chart
![image](https://user-images.githubusercontent.com/68850993/127125009-29a479bf-74e5-45e2-8c00-dacddfe39f01.png)

