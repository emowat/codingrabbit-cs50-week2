## Problem to Solve

In a substitution cipher, we "encrypt" a message by replacing every letter with another letter. To do so, we use a key: in this case, a mapping of each of the letters of the alphabet to the letter it should correspond to when we encrypt it. 

A key, for example, might be the string `NQXPOMAFTRHLZGECYJIUWSKDVB`. This 26-character key means that `A` (the first letter of the alphabet) should be converted into `N` (the first character of the key), `B` (the second letter of the alphabet) should be converted into `Q` (the second character of the key), and so forth.

In a file called `substitution.c` in a folder called `substitution`, create a program that enables you to encrypt messages using a substitution cipher. At the time the user executes the program, they should decide, by providing a command-line argument, on what the key should be.

*For the full background on substitution ciphers and detailed walkthroughs, read the official instructions here: [CS50 Substitution Instructions](https://cs50.harvard.edu/x/psets/2/substitution/)*

## Instructions

If you are unsure where to start, break the problem down into these smaller steps:

1. **Check Command-Line Arguments:** 
   Your program must accept a *single* command-line argument (the key). Modify `main(int argc, string argv[])` to check that `argc == 2`. If not, print an error message (like `Usage: ./substitution key`) and return `1`.
2. **Validate the Key:** 
   The key must meet several conditions to be valid. You must check that the key:
   *   Has exactly 26 characters (Hint: `strlen`).
   *   Contains only alphabetic characters (Hint: `isalpha`).
   *   Does not contain repeated characters (Hint: loop through and compare each character to the rest).
   If any of these fail, print an error message and return `1`.
3. **Prompt for Plaintext:**
   Use `get_string` to ask the user for plaintext.
4. **Encrypt the Text:** 
   Iterate over each character in the user's plaintext. 
   *   If it's an alphabetical character, find its position in the alphabet (e.g. `A` is 0, `B` is 1), and then use that position as an index into the user's key to find the substitution character.
   *   Ensure you preserve the case! If the original letter was uppercase, the substituted letter should be uppercase (Hint: `toupper` or `tolower`).
   *   If the character is not alphabetical (e.g. punctuation, spaces), leave it unchanged.
5. **Print the Ciphertext:** 
   Print the resulting ciphertext string, followed by a newline!

## How to Begin

Open the terminal window at the bottom of your screen. Execute the following command to change directories into the `substitution` folder:

```bash
cd substitution
```

You can now execute the `code` command to create a new file and open it in the editor:

```bash
code substitution.c
```

## How to Test

Recall that you can compile your program by running:

```bash
make substitution
```

If it compiles successfully, run your program with a key:

```bash
./substitution VCHPRZGJNTLSKFBDQWAXEUYMOI
```

Test it with some example inputs:
```text
$ ./substitution VCHPRZGJNTLSKFBDQWAXEUYMOI
plaintext:  hello, world
ciphertext: jvkks, pvykq

$ ./substitution 
Usage: ./substitution key

$ ./substitution ABC
Key must contain 26 characters.
```

If you see an error message or get stuck, remember to **click the Coding Rabbit icon** on the left sidebar to ask your AI Teaching Assistant for help!
