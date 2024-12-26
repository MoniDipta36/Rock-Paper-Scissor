# Rock-Paper-Scissor
import random

list_choices = ["rock", "paper", "scissors"]
computer_wins = 0
user_wins = 0
draws = 0

while True:
    question = input("Do you want to play? (yes/no) ").lower()

    if question == "no":
        print("Thank you")
        break
    elif question != "yes":
        print("NO NO NO! Please enter 'yes' or 'no'.")
        continue

    print("Let's go!")
    computer_choice = random.choice(list_choices)
    user_choice = input("Enter your pick (rock, paper, scissors): ").lower()

    if user_choice not in list_choices:
        print("Invalid choice. Please try again.")
        continue

    print(f"User pick: {user_choice}")
    print(f"Computer pick: {computer_choice}")

    if user_choice == computer_choice:
        print("It's a draw!")
        draws += 1
    elif (user_choice == "rock" and computer_choice == "scissors") or \
         (user_choice == "paper" and computer_choice == "rock") or \
         (user_choice == "scissors" and computer_choice == "paper"):
        print("You win!")
        user_wins += 1
    else:
        print("Computer wins!")
        computer_wins += 1

    play_again = input("Do you want to play again? (yes/no) ").lower()
    if play_again != "yes":
        print("Thank you for playing!")
        break

print("\nFinal Results:")
print(f"Computer wins: {computer_wins}")
print(f"Your wins: {user_wins}")
print(f"Draws: {draws}")
