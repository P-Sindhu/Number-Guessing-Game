# Number-Guessing-Game
Enjoy a fun guessing game with computer hints for added excitement.

```python
import random
```
This line imports the `random` module in Python, which allows us to generate random numbers. We'll use this module to generate a random number for the player to guess.

```python
def number_guessing_game():
```
This line defines a function named `number_guessing_game()`. This function encapsulates the logic of the number guessing game.

```python
    print("Welcome to the Number Guessing Game!")
    print("I'm thinking of a number between 1 and 100. Can you guess it?")
```
These lines print a welcome message and instructions for the player at the beginning of the game.

```python
    secret_number = random.randint(1, 100)
```
This line generates a random integer between 1 and 100 (inclusive) and assigns it to the variable `secret_number`. This is the number that the player needs to guess.

```python
    attempts = 0
```
This line initializes a variable `attempts` to keep track of the number of attempts made by the player.

```python
    while True:
```
This line starts an infinite loop. The game will continue until the player either guesses the correct number or chooses to exit.

```python
        guess = input("Enter your guess (or 'exit' to quit): ")
```
This line prompts the player to enter their guess or type 'exit' to quit the game.

```python
        if guess.lower() == 'exit':
            print("Quitting the game. The number was:", secret_number)
            break
```
This block of code checks if the player entered 'exit'. If so, it prints a message indicating the game is quitting and reveals the secret number. Then it breaks out of the loop, ending the game.

```python
        try:
            guess = int(guess)
        except ValueError:
            print("Please enter a valid number.")
            continue
```
This block of code tries to convert the player's input into an integer. If the input cannot be converted (e.g., if the player enters a word instead of a number), a `ValueError` exception is raised. In that case, it prints a message asking the player to enter a valid number and continues to the next iteration of the loop.

```python
        attempts += 1
```
This line increments the `attempts` variable by 1 for each guess the player makes.

```python
        if guess < secret_number:
            print("Too low! Try again.")
        elif guess > secret_number:
            print("Too high! Try again.")
        else:
            print("Congratulations! You guessed the number in", attempts, "attempts!")
            break
```
This block of code compares the player's guess with the `secret_number`. If the guess is lower than the secret number, it prints "Too low! Try again.". If the guess is higher, it prints "Too high! Try again.". If the guess is correct, it prints a congratulatory message indicating the number of attempts made, and then it breaks out of the loop, ending the game.

```python
number_guessing_game()
```
This line calls the `number_guessing_game()` function, starting the game when the script is executed.
