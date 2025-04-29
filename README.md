🎮 Number Guessing Snake Game (Python)

A fun twist on the classic number guessing game, enhanced with Snake game mechanics using Python. This hybrid project challenges players to guess the correct number while navigating a snake through obstacles, combining logic with reflex-based gameplay. Great for learning control flow, random number generation, and basic game development in Python.

Features:

Random number generation with guess validation

Snake game integration for added challenge

Interactive CLI or graphical interface (optional)

Great practice for beginners in Python game dev

Code :-

    import random

    def number_guessing_game():
    print("Welcome to the Number Guessing Game!")
    
    # Set the range for the random number
    lower_bound = 1
    upper_bound = 100
    secret_number = random.randint(lower_bound, upper_bound)
    
    attempts = 0
    max_attempts = 10  # You can change the number of attempts allowed

    print(f"I have selected a number between {lower_bound} and {upper_bound}.")
    print(f"You have {max_attempts} attempts to guess it.")

    while attempts < max_attempts:
        try:
            guess = int(input("Enter your guess: "))
            attempts += 1
            
            if guess < lower_bound or guess > upper_bound:
                print(f"Please guess a number between {lower_bound} and {upper_bound}.")
                continue
            
            if guess < secret_number:
                print("Too low! Try again.")
            elif guess > secret_number:
                print("Too high! Try again.")
            else:
                print(f"Congratulations! You've guessed the number {secret_number} in {attempts} attempts.")
                break
        except ValueError:
            print("Invalid input! Please enter a valid integer.")

    if attempts == max_attempts:
        print(f"Sorry, you've used all your attempts. The number was {secret_number}.")

    if __name__ == "__main__":
    number_guessing_game()
