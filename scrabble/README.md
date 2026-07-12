## Problem to Solve

In the game of [Scrabble](https://en.wikipedia.org/wiki/Scrabble), players create words to score points, and the number of points is the sum of the point values of each letter in the word.

For example, if we wanted to score the word “CODE”, we would note that the ‘C’ is worth 3 points, the ‘O’ is worth 1 point, the ‘D’ is worth 2 points, and the ‘E’ is worth 1 point. Summing these, we get that “CODE” is worth 7 points.

In a file called `scrabble.c` in a folder called `scrabble`, implement a program in C that determines the winner of a short Scrabble-like game. Your program should prompt for input twice: once for "Player 1" to input their word and once for "Player 2" to input their word. Then, depending on which player scores the most points, your program should either print "Player 1 wins!", "Player 2 wins!", or "Tie!" (in the event the two players score equal points).

*For the full background on Scrabble and detailed hints on how to implement your program, read the official instructions here: [CS50 Scrabble Instructions](https://cs50.harvard.edu/x/psets/2/scrabble/)*

## Instructions

If you are unsure where to start, break the problem down into these smaller steps:

1. **Prompt for Input:** Prompt both "Player 1" and "Player 2" for their words using `get_string`.
2. **Compute the Score:** Write a helper function `compute_score(string word)` that calculates and returns the point value for a given word. You can use an array `int POINTS[] = {1, 3, 3, 2, 1, 4, 2, 4, 1, 8, 5, 1, 3, 1, 1, 3, 10, 1, 1, 1, 1, 4, 4, 8, 4, 10};` to help map a letter to its points.
3. **Handle Uppercase vs Lowercase:** A lowercase 'a' and uppercase 'A' are both worth 1 point. You'll need to figure out how to map characters to the `POINTS` array correctly. (Hint: Look into `isupper`, `islower`, or `toupper`!)
4. **Ignore Punctuation:** Any character that is not a letter (like `!` or `?`) should be given 0 points.
5. **Print the Winner:** Compare the two scores you calculated, and print "Player 1 wins!", "Player 2 wins!", or "Tie!".

## How to Begin

Open the terminal window at the bottom of your screen. Execute the following command to change directories into the `scrabble` folder:

```bash
cd scrabble
```

You can now execute the `code` command to create a new file and open it in the editor:

```bash
code scrabble.c
```

## How to Test

Recall that you can compile your program by running:

```bash
make scrabble
```

If it compiles successfully, run your program with:

```bash
./scrabble
```

Test it with some example inputs:
```text
Player 1: Question?
Player 2: Question!
Tie!

Player 1: red
Player 2: wheelbarrow
Player 2 wins!
```

If you see an error message or get stuck, remember to **click the Coding Rabbit icon** on the left sidebar to ask your AI Teaching Assistant for help!
