## Problem to Solve

Supposedly, Caesar (yes, that Caesar) used to "encrypt" confidential messages by shifting each letter therein by some number of places. For instance, he might write A as B, B as C, C as D, …, and, wrapping around alphabetically, Z as A. 

To say HELLO to someone with a key of `1`, Caesar might write IFMMP instead. Upon receiving such messages from Caesar, recipients would have to “decrypt” them by shifting letters in the opposite direction by the same number of places.

In a file called `caesar.c` in a folder called `caesar`, write a program that enables you to encrypt messages using Caesar’s cipher. At the time the user executes the program, they should decide, by providing a command-line argument, what the key should be. Then your program should prompt for the plaintext and output the ciphertext.

*For the full background on Caesar's cipher and a detailed walkthrough, read the official instructions here: [CS50 Caesar Instructions](https://cs50.harvard.edu/x/psets/2/caesar/)*

## Instructions

If you are unsure where to start, break the problem down into these smaller steps:

1. **Check Command-Line Arguments:** 
   Your program must accept a *single* command-line argument (the key). Modify `main(int argc, string argv[])` to check that `argc == 2`. If not, print an error message (like `Usage: ./caesar key`) and `return 1;` from main.
2. **Validate the Key:** 
   Write a helper function `bool only_digits(string s)` that loops through the provided key (`argv[1]`) and checks if every character is a digit (Hint: `isdigit`). If the user typed something like `./caesar banana`, your program should print `Usage: ./caesar key` and return 1.
3. **Convert the Key to an Integer:** 
   The command-line argument `argv[1]` is a `string`. You need it to be an `int`. Use the `atoi` function (from `<stdlib.h>`) to convert it!
4. **Prompt for Plaintext & Rotate:**
   Use `get_string` to ask the user for plaintext. Then, write a function `char rotate(char c, int n)` that rotates a single character by `n` positions.
   *   If `c` is alphabetical, shift it. Be sure to preserve the case! (If `c` is uppercase, subtract `'A'`, add the key, modulo 26, then add `'A'` back).
   *   If `c` is not alphabetical (e.g. punctuation, spaces), just return `c` unchanged.
5. **Print the Ciphertext:** 
   Loop through every character of the user's plaintext, call your `rotate` function, and print the resulting ciphertext. Remember to print a newline at the end!

## How to Begin

Open the terminal window at the bottom of your screen. Execute the following command to change directories into the `caesar` folder:

```bash
cd caesar
```

You can now execute the `code` command to create a new file and open it in the editor:

```bash
code caesar.c
```

## How to Test

Recall that you can compile your program by running:

```bash
make caesar
```

If it compiles successfully, run your program with a key:

```bash
./caesar 13
```

Test it with some example inputs:
```text
$ ./caesar 1
plaintext:  HELLO
ciphertext: IFMMP

$ ./caesar 13
plaintext:  be sure to drink your Ovaltine
ciphertext: or fher gb qevax lbhe Binygvar

$ ./caesar banana
Usage: ./caesar key
```

If you see an error message or get stuck, remember to **click the Coding Rabbit icon** on the left sidebar to ask your AI Teaching Assistant for help!
