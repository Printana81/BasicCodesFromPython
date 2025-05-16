# BasicCodesFromPython
Hello everyone! Here I upload my python codes.
# Global scores
player1_score = 0
player2_score = 0

# Function to compare choices and update score
def score_compare(player_1, player_2):
    global player1_score, player2_score

    if player_1 == player_2:
        print("It's a tie!")
    elif (player_1 == 'r' and player_2 == 's') or \
         (player_1 == 'p' and player_2 == 'r') or \
         (player_1 == 's' and player_2 == 'p'):
        print("Player 1 wins the round!")
        player1_score += 1
    else:
        print("Player 2 wins the round!")
        player2_score += 1

# Main game function
def play_game():
    print("Enter 'r' for rock, 'p' for paper, or 's' for scissors.")
    for round_num in range(1, 11):
        print(f"\nRound {round_num}")
        player_1 = input("Player 1's turn: ").lower()
        player_2 = input("Player 2's turn: ").lower()

        if player_1 not in ['r', 'p', 's'] or player_2 not in ['r', 'p', 's']:
            print("Invalid input. Please enter r, p, or s.")
            continue

        score_compare(player_1, player_2)

    print("\nGame Over!")
    print(f"Final Score - Player 1: {player1_score}, Player 2: {player2_score}")
    if player1_score > player2_score:
        print("Player 1 is the winner!")
    elif player2_score > player1_score:
        print("Player 2 is the winner!")
    else:
        print("It's a draw!")

# Run the game
play_game()
