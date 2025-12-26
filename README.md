# Task-2



import random

def guessing_game():
    # Generate a random number between 1 and 100
    number_to_guess = random.randint(1, 100)
    attempts = 0

    print("Welcome to the Number Guessing Game!")
    print("I'm thinking of a number between 1 and 100.")

    while True:
        # Ask user for their guess
        user_guess = input("Enter your guess: ")

        # Validate user input
        try:
            user_guess = int(user_guess)
        except ValueError:
            print("Invalid input. Please enter a number.")
            continue

        # Check if the guess is correct
        attempts += 1
        if user_guess == number_to_guess:
            print(f"Congratulations! You found the number in {attempts} attempts.")
            break
        elif user_guess < number_to_guess:
            print("Too low! Try again.")
        else:
            print("Too high! Try again.")

def main():
    play_again = 'y'
    while play_again.lower() == 'y':
        guessing_game()
        play_again = input("Do you want to play again? (y/n): ")

if __name__ == "__main__":
    main()