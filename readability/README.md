## Problem to Solve

According to [Scholastic](https://www.scholastic.com/teachers/teaching-tools/collections/guided-reading-book-lists-for-every-level.html), E.B. White’s *Charlotte’s Web* is between a second- and fourth-grade reading level, and Lois Lowry’s *The Giver* is between an eighth- and twelfth-grade reading level. What does it mean, though, for a book to be at a particular reading level?

In a file called `readability.c` in a folder called `readability`, you’ll implement a program that calculates the approximate grade level needed to comprehend some text using the **Coleman-Liau index**. Your program should prompt the user for a string of text, compute the index, and print as output "Grade X" where "X" is the grade level computed, rounded to the nearest integer. 

If the grade level is 16 or higher, your program should output "Grade 16+". If the grade level is less than 1, your program should output "Before Grade 1".

*For the full background on Readability tests and the Coleman-Liau index formula, read the official instructions here: [CS50 Readability Instructions](https://cs50.harvard.edu/x/psets/2/readability/)*

## Instructions

The Coleman-Liau index formula is:
```c
index = 0.0588 * L - 0.296 * S - 15.8
```
*   `L` is the average number of letters per 100 words in the text.
*   `S` is the average number of sentences per 100 words in the text.

If you are unsure where to start, break the problem down into these smaller steps:

1. **Prompt for Text:** Use `get_string` to prompt the user for the text they want to analyze.
2. **Count Letters, Words, and Sentences:** 
   *   Write a function `count_letters(string text)` that returns the number of letters (ignoring punctuation/spaces). (Hint: `isalpha` might be useful).
   *   Write a function `count_words(string text)` that returns the number of words. You can assume any sequence of characters separated by a space is a word.
   *   Write a function `count_sentences(string text)` that returns the number of sentences. You can assume any sequence of characters ending with a `.`, `!`, or `?` is a sentence.
3. **Compute the Index:** Calculate `L` and `S`, then plug them into the Coleman-Liau formula. Be careful with integer division! You may want to cast your `int` values to `float` before doing division.
4. **Print the Grade Level:** Round the resulting index to the nearest whole number (using `round` from `math.h`), and print the result using the formatting rules described above.

## How to Begin

Open the terminal window at the bottom of your screen. Execute the following command to change directories into the `readability` folder:

```bash
cd readability
```

You can now execute the `code` command to create a new file and open it in the editor:

```bash
code readability.c
```

## How to Test

Recall that you can compile your program by running:

```bash
make readability
```

If it compiles successfully, run your program with:

```bash
./readability
```

Test it with some example inputs:
```text
Text: One fish. Two fish. Red fish. Blue fish.
Before Grade 1

Text: Congratulations! Today is your day. You're off to Great Places! You're off and away!
Grade 3

Text: Harry Potter was a highly unusual boy in many ways. For one thing, he hated the summer holidays more than any other time of year. For another, he really wanted to do his homework, but was forced to do it in secret, in the dead of the night. And he also happened to be a wizard.
Grade 5
```

If you see an error message or get stuck, remember to **click the Coding Rabbit icon** on the left sidebar to ask your AI Teaching Assistant for help!
