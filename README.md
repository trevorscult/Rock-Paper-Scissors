#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main()
{
    int player_choice, computer_choice;
    srand(time(0)); // seed the random number generator with current time

    printf("Let's play rock-paper-scissors!\n");
    printf("Choose:\n 1 for rock\n 2 for paper\n 3 for scissors\n");

    do {
        printf("Enter your choice (1-3): ");
        scanf("%d", &player_choice);
    } while (player_choice < 1 || player_choice > 3);

    computer_choice = rand() % 3 + 1; // generate a random choice for computer

    printf("You chose ");

    switch (player_choice) {
        case 1:
            printf("rock");
            break;
        case 2:
            printf("paper");
            break;
        case 3:
            printf("scissors");
            break;
    }

    printf(" and the computer chose ");

    switch (computer_choice) {
        case 1:
            printf("rock");
            break;
        case 2:
            printf("paper");
            break;
        case 3:
            printf("scissors");
            break;
    }

    // determine the winner
    if (player_choice == computer_choice) {
        printf("\nIt's a tie!");
    } else if (player_choice == 1 && computer_choice == 3 ||
               player_choice == 2 && computer_choice == 1 ||
               player_choice == 3 && computer_choice == 2) {
        printf("\nYou win!");
    } else {
        printf("\nThe computer wins!");
    }

    return 0;
}

