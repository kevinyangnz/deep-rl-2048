# Deep Reinforcement Learning for 2048

Deep Reinforcement Learning (Deep RL) using the PPO algorithm to play the 2048 game. 

## Game Overview

2048 is a grid-based puzzle game where you have 4x4 board and must use arrow keys to move all the tiles a certain direction. You must merge tiles of the same number to combine into tiles of double the value. The aim of the game is to reach a 2048 tile, although the game will only end when you no longer have any valid moves. 


## Approach

Initially, I tried using the Reinforce algorithm. However I quickly began to realise the complexity of the 2048 game and decided to apply the more sophisticated PPO algorithm. 



## Reward Shaping

In a game of 2048, the player receives an increment to their score equal to the value of every new merged tile created, which exponentially grows the score. Therefore this Deep RL implementation uses the log of the score alongside the following extra rewards and penalties:


| Variable        | Reward/Penalty            | Details                                                                                                                                                 |
|-----------------|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| move_penalty    | -2                        | Apply a -2 penalty to every move made. <br>Encourages the agent to make the most of each move.                                                          |
| empty_bonus     | -(game.empty_tiles * 0.1) | game.empty_tiles represents the number of empty tiles in the board at each action. <br>Penalises the agent for having many occupied tiles in the board. |
| corner_bonus    | 1                         | Rewards the agent for keeping the largest tile in a corner.                                                                                             |
| milestone_bonus | 1                         | Rewards the agent for reaching tile milestones (128, 256, 512, 1024, 2048)                                                                              |


## Results



## Next Steps

