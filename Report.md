
## DRL - DDPG Algorithm - Reacher Continuous Control

### Model Architecture
The Udacity provided DDPG code in PyTorch was used and adapted for the 1 agent environment.

The algorithm uses two deep neural networks (actor-critic) with the following struture:
- Actor    
    - Hidden: (input, 400)  - ReLU
    - Hidden: (400, 300)    - ReLU
    - Output: (300, 4)      - TanH

- Critic
    - Hidden: (input, 400)              - ReLU
    - Hidden: (400 + action_size, 300)  - ReLU
    - Output: (300, 1)                  - Linear


### Hyperparameters
- Learning Rate: 1e-3 (for Critic and Actor)
- Batch Size: 128
- Replay Buffer: 1e6
- Gamma: 0.99
- Tau: 1e-3
- LEARN_EVERY = 20        # learning timestep interval
- LEARN_NUM = 10            # number of learning passes
- Ornstein-Uhlenbeck noise parameters (0.15 theta and 0.2 sigma.)
- Critic network was trained with gradient clipping


## Results and Future Work
The current model achieved quite good results. The task was solved after 842 episodes. The score increased more or less monotonously. During the subsequent testing of the algorithm, scores above 30 were frequently achieved

<img width="400" alt="Bildschirmfoto 2022-11-14 um 22 57 27" src="https://user-images.githubusercontent.com/100682506/201776617-0906a333-c4ba-4c36-b324-2f31c6b71d08.png">


I plan to now implement the D4PG for the 20 parallel agents. Then I would like test it in both environments, the reacher and the crawler.
The goal is to find when and where each of the algorithms have the best performance.
