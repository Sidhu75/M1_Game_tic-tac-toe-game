
TIC-TAC-TOE
## Introduction
1. This is a simple tic-tac-toe game made in C language :
The game is to be played between two people (in this program between HUMAN and COMPUTER).
One of the player chooses ‘O’ and the other ‘X’ to mark their respective cells.
The game starts with one of the players and the game ends when one of the players has one whole row/ column/ diagonal filled with his/her respective character (‘O’ or ‘X’).
If no one wins, then the game is said to be draw.
2. Our project name is Tic-Tac-Toe game. This game is very popular and is
fairly simple by itself. It is actually a two player game. In this game, there is
a board with n x n squares. In our game, it is 3 x 3 squares.
The goal of Tic-Tac-Toe is to be one of the players to get three same
symbols in a row - horizontally, vertically or diagonally - on a 3 x 3 grid

## RESEARCH

It is often used as a pedagogical tool for teaching the concepts of good sportsmanship and the branch of artificial intelligence that deals with the searching of game trees. It is straightforward to write a computer program to play tic-tac-toe perfectly or to enumerate the 765 essentially different positions (the state space complexity) or the 26,830 possible games up to rotations and reflections (the game tree complexity) on this space. If played optimally by both players, the game always ends in a draw, making tic-tac-toe a futile game.

## FEATURES
The game is played on a grid that's 3 squares by 3 squares. You are X, your friend (or the computer in this case) is O. Players take turns putting their marks in empty squares. The first player to get 3 of her marks in a row (up, down, across, or diagonally) is the winner. When all 9 squares are full, the game is over.


## SWOT Analysis

 Strength :
1. To feel relax and  stress free we can play this game.
2. This game is for fun purpose.
3. We can access this game anytime.
4. Perfect for basic programming exercises at initial stage of your learning process .

Weakness :
1. Playing game for hours can cause a trouble for eyes.
2. This may lead eye problems.
3. limited Features .
 



## 4W's and 1'H

4W's

Who : Can be played anytime.


What : Virtual medium to  play the game.


When : Can be played from anywhere.


Where : Everyone can play this game.


1'H

How : Can be operated from Personal computer or laptop.

      




## Detail Requirements :

## High Level Requirements :
| ID | Description | Status |
| --- | --- | --- |
| HLR_1 | The user can change its selected sign("0","x"). | Implemented |

## Low Level Requiremnets :
| ID | Description | Status |
| --- | --- | --- |
| LLR_1 | List of operations displayed | Implemented |
| LLR_2 | Input from the user. | Implemented |
| LLR_3 |Exit the program . | Implemented |


## behavioural Diagram

![Structural Diagram](https://user-images.githubusercontent.com/82743874/142980247-85675c44-f339-40d9-bba6-f746ae136bab.JPG)


## Stuctural Diagram

![Activity Diagram](https://user-images.githubusercontent.com/82743874/142980104-de757f3b-4652-42b7-a778-303b952c0514.JPG)

## test file


#include <stdio.h>

#include <conio.h>

char square[10] = { 'o', '1', '2', '3', '4', '5', '6', '7', '8', '9' };

int checkwin();
void board();

int main()
{
    int player = 1, i, choice;

    char mark;
    do
    {
        board();
        player = (player % 2) ? 1 : 2;

        printf("Player %d, enter a number:  ", player);
        scanf("%d", &choice);

        mark = (player == 1) ? 'X' : 'O';

        if (choice == 1 && square[1] == '1')
            square[1] = mark;

        else if (choice == 2 && square[2] == '2')
            square[2] = mark;

        else if (choice == 3 && square[3] == '3')
            square[3] = mark;

        else if (choice == 4 && square[4] == '4')
            square[4] = mark;

        else if (choice == 5 && square[5] == '5')
            square[5] = mark;

        else if (choice == 6 && square[6] == '6')
            square[6] = mark;

        else if (choice == 7 && square[7] == '7')
            square[7] = mark;

        else if (choice == 8 && square[8] == '8')
            square[8] = mark;

        else if (choice == 9 && square[9] == '9')
            square[9] = mark;

        else
        {
            printf("Invalid move ");

            player--;
            getch();
        }
        i = checkwin();

        player++;
    }while (i ==  - 1);

    board();

    if (i == 1)
        printf("==>\aPlayer %d win ", --player);
    else
        printf("==>\aGame draw");

    getch();

    return 0;
}

/*********************************************

FUNCTION TO RETURN GAME STATUS
1 FOR GAME IS OVER WITH RESULT
-1 FOR GAME IS IN PROGRESS
O GAME IS OVER AND NO RESULT
 **********************************************/

int checkwin()
{
    if (square[1] == square[2] && square[2] == square[3])
        return 1;

    else if (square[4] == square[5] && square[5] == square[6])
        return 1;

    else if (square[7] == square[8] && square[8] == square[9])
        return 1;

    else if (square[1] == square[4] && square[4] == square[7])
        return 1;

    else if (square[2] == square[5] && square[5] == square[8])
        return 1;

    else if (square[3] == square[6] && square[6] == square[9])
        return 1;

    else if (square[1] == square[5] && square[5] == square[9])
        return 1;

    else if (square[3] == square[5] && square[5] == square[7])
        return 1;

    else if (square[1] != '1' && square[2] != '2' && square[3] != '3' &&
        square[4] != '4' && square[5] != '5' && square[6] != '6' && square[7]
        != '7' && square[8] != '8' && square[9] != '9')

        return 0;
    else
        return  - 1;
}


/*******************************************************************
FUNCTION TO DRAW BOARD OF TIC TAC TOE WITH PLAYERS MARK
 ********************************************************************/


void board()
{
    system("cls");
    printf("\n\n\tTic Tac Toe\n\n");

    printf("Player 1 (X)  -  Player 2 (O)\n\n\n");


    printf("     |     |     \n");
    printf("  %c  |  %c  |  %c \n", square[1], square[2], square[3]);

    printf("_____|_____|_____\n");
    printf("     |     |     \n");

    printf("  %c  |  %c  |  %c \n", square[4], square[5], square[6]);

    printf("_____|_____|_____\n");
    printf("     |     |     \n");

    printf("  %c  |  %c  |  %c \n", square[7], square[8], square[9]);

    printf("     |     |     \n\n");
}


## ##TEST PLAN

## Table No 1: High level test plan

| Test ID | Description | Exp I/P | Exp O/p |
| ------- | ----------- | ------- | ------- |
| H_01 | Check if the graph for playing is being drawn or not. | No input. | 3X3 graph is drawn. |
| H_02 | Check if player/computer got 3 of his inputs in vertical, horizontal or diagonal format. | 'X' or 'O' i/p from the user/computer. | The user/computer won the game. |
| H_03 | Check for draw. | 9 inputs from (user+computer). | The game is over. |

## Table No 2: Low level test plan

| Test ID | Description | Exp I/P | Exp O/p |
| ------- | ----------- | ------- | ------- |
| L_01 | Checking for the basic requirement to the game, i.e., a 3X3 graph is drawn or not. This 3X3 graph is the basic need to play the game as it is like a game board for the game. |	Not input expected from the user.	| 3X3 graph is drawn. |
| L_02 |	Play proceeds with the user/computer alternately placing their marks in any unoccupied cell. Check if any player/computer finishes with 3 marks in a row(vertical, horizontal or diagonal). |	'X' or 'O' i/p from the user/computer. |	The user/computer won the game. |
| L_03 |	Check if a total of 9 moves have been made( combining that of user and computer), the game ends up in a draw when neither the user nor the computer is able to get 3 marks in a row. |	9 inputs from (user+computer). |	The game is over. Somebody won or the game ended as a draw. |





# Case 1:
![image](https://user-images.githubusercontent.com/67543660/143075024-a43121fe-0d38-492b-acaf-7885357e332f.png)

# Case 2:
![image](https://user-images.githubusercontent.com/67543660/143075153-26733c15-70b1-4f0a-970e-a75bac524523.png)

# Case 3:
![image](https://user-images.githubusercontent.com/67543660/143075244-e8c62770-fb36-4ada-b48a-88a70bedfb87.png)

# Case 4:
![image](https://user-images.githubusercontent.com/67543660/143075346-b02f4bb5-3681-4617-bd9f-f5b884eade87.png)


## Output


## 1
![2021-11-23 (8)](https://user-images.githubusercontent.com/94374211/143075219-6c49f019-1d06-4fdd-b6e2-87678c27cbba.png)
## 2
![2021-11-23 (9)](https://user-images.githubusercontent.com/94374211/143075359-8e75e6b7-27d2-4c29-874c-29207c30f4c3.png)
## 3
![2021-11-23 (10)](https://user-images.githubusercontent.com/94374211/143076015-373c464f-ac10-475c-9dd0-aceae55b4350.png)
## 4
![2021-11-23 (11)](https://user-images.githubusercontent.com/94374211/143076209-183736f1-eea9-4c00-8ee8-5686fe97e806.png)
## 5
![2021-11-23 (12)](https://user-images.githubusercontent.com/94374211/143076365-14a0cf95-e31c-4546-8e88-a3b4dd37eef7.png)




/*******************************************************************
END OF PROJECT
 ********************************************************************/
