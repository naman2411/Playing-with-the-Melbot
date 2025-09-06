# Playing With The Melbot

This repository contains the implementation of a decision tree learning algorithm for playing the word-guessing game with Melbot. Melbot is a toy that helps improve vocabulary by challenging players to guess a secret word from a given dictionary. The goal is to develop an algorithm that can effectively guess the secret word within a limited number of queries.

## Game Rules

1. Melbot selects a word from the dictionary as the secret word for each round.
2. Melbot reveals the length of the secret word to the player using underscores, representing each character's position.
3. The player (Melbo) makes queries by guessing words from the dictionary.
   - If the query index is invalid, the round terminates.
   - If the query word matches the secret word, the round terminates, and the win count is incremented.
   - If the query word is not the secret word and the maximum number of queries is reached (Q = 15), the round terminates.
   - If the query word is not the secret word but the maximum number of queries is not reached, Melbot reveals common characters between the query word and the secret word.
     - Characters that match both in value and position are revealed, and other positions are represented by underscores.
4. Melbo plays N rounds, one with each word from the dictionary.

## Task

The task is to develop a decision tree learning algorithm that can effectively play the word-guessing game. The algorithm should make informed queries to guess the secret word within the query limit and maximize the win rate.

## Files

- `submit.py`: Contains the code implementing the decision tree learning algorithm.
  - The `my_fit()` method takes a dictionary as a list of words and returns a trained decision tree as a model.
  - The trained decision tree model consists of tree and node objects.
  - Each node implements the `get_child()` method to decide which child node to move to based on the response.
  - Each node (leaf and non-leaf) implements the `get_query()` method to determine the query Melbo should ask when at that node.
- `dummy_submit.py`: A sample submission file demonstrating the implementation of the decision tree algorithm.
- `validation_code.ipynb`: A Google Colab notebook demonstrating the usage and validation of the decision tree algorithm.

## Evaluation Measures

The algorithm will be evaluated based on the following measures:

1. Training Speed: The time taken by the `my_fit()` method to finish training.
2. Model Size: The on-disk size of the trained model after a pickle dump.
3. Average Queries: The average number of queries made by the model per round.
4. Win Rate: The percentage of correct guesses within the query limit for the secret dictionary.

## Solution Strategies

The following strategies can be considered while developing the decision tree learning algorithm:

1. Lookahead: Instead of choosing the split that maximizes entropy reduction immediately, consider splits that result in maximum entropy reduction a few levels down the tree.
2. Minimizing Queries: Aim to minimize the number of queries required to correctly guess the word and improve the win rate.
3. Balanced Splits: Consider splits that balance entropy reduction, expected time to success, and regularization to prevent imbalanced splits.

Please refer to the problem statement for more details and instructions on the algorithm's design decisions.

## Conclusion

The "Playing With The Melbot" repository provides an implementation of a decision tree learning algorithm for the word-guessing game with Melbot. It aims to maximize the win rate by making informed queries within the query limit. Feel free to explore the code and experiment with different strategies to improve the algorithm's performance.

For further information and instructions, please refer to the provided files and the problem statement.
