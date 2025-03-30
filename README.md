# Nim - Reinforcement Learning AI

## Project Overview
This project implements an AI agent that learns to play the game of Nim through reinforcement learning, specifically using the Q-learning algorithm. The AI trains by playing against itself repeatedly, learning optimal strategies through experience.

## Background: The Game of Nim
In Nim, players take turns removing objects from piles:
- The game starts with some number of piles, each containing some number of objects
- On each turn, a player must remove any non-negative number of objects from a single non-empty pile
- The player who removes the last object loses the game

While the strategy for a single pile is straightforward, the optimal strategy for multiple piles is more complex. This project uses Q-learning to discover winning strategies.

## Implementation Details

### Key Components
- **Nim Class**: Handles the game mechanics, including tracking piles, current player, and determining available actions
- **NimAI Class**: Implements the Q-learning algorithm to train an AI to play Nim optimally
- **Training Function**: Runs simulated games between the AI and itself to build Q-values
- **Play Function**: Allows a human player to play against the trained AI

### Q-Learning Implementation
The AI learns by associating a numerical value (Q-value) with each (state, action) pair, where:
- A **state** is represented as a list of pile sizes (e.g., [1, 1, 3, 5])
- An **action** is represented as a tuple (i, j), where i is the pile index and j is the number of objects to remove

The Q-learning formula used is:
```
Q(s, a) ← Q(s, a) + α * (new value estimate - old value estimate)
```
Where:
- α (alpha) is the learning rate
- The new value estimate is the immediate reward plus estimated future rewards
- The old value estimate is the existing Q-value

### Key Functions Implemented
1. `get_q_value`: Returns the Q-value for a given state-action pair
2. `update_q_value`: Updates Q-values based on rewards and future estimates
3. `best_future_reward`: Determines the best possible future reward from a given state
4. `choose_action`: Selects an action using either greedy or epsilon-greedy approach

## How to Use

### Requirements
- Python 3.x
- No external libraries required beyond Python's standard library

### Running the Program
1. Train the AI:
   ```python
   python nim.py
   ```

2. Play against the AI:
   ```python
   python play.py
   ```

### Testing
You can test your implementation using CS50's check50 tool:
```
check50 ai50/projects/2024/x/nim
```

## Project Structure
- `nim.py`: Contains the main implementation of the Nim game and AI
- `play.py`: Interface for playing against the trained AI

## Learning Outcomes
Through this project, you'll gain:
- Understanding of reinforcement learning concepts
- Experience implementing Q-learning algorithms
- Insights into how AI can learn game strategies through self-play

## Credits
This project is part of CS50's Introduction to Artificial Intelligence with Python course.
