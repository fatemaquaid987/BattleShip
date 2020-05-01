# BattleShip #  

## Overview

BattleShip is an interactive web application made using HTML5, CSS3, JavaScript and, the DOM.
This game assumes that only one user is viewing the page that presents the game at a time (e.g., the two players are using a laptop that they pass back and forth between turns). Details of the game can be found [here](https://en.wikipedia.org/wiki/Battleship_(game)). The game consists of 2 10x10 grids, with rows labeled 1-10 and columns labeled A-J. The players will place 3 game pieces: an aircraft carrier (5 spaces long), a battleship (4 spaces long), and a submarine (3 spaces long). These pieces can be placed either horizontally or vertically.  

## How to run

Open the html file in Google Chrome to start playing the game.  

## How to play

When the page is loaded, the game begins by asking the first player for their name and a string representing their ship placements. The game only accepts 3 different formats for ship placements. For example: the game accepts *only* the strings of the following forms as equivalent, with each resulting in an aircraft carrier placed on A1, A2, A3, A4, A5; a battleship at B6, C6, D6, E6; and a submarine at H3, I3, J3:  
A:A1-A5;B:B6-E6; S:H3-J3  
A(A1-A5); B(B6-E6); S(H3-J3);  
B(B6-E6);S(H3-J3);A(A1-A5)  
Any syntax other than the above 3 will not be accepted.  

After gathering the first player's name and ship placement, the game will prompt the second player for their name and ship placement.  

With this starting info in hand, the game will begin the first player's turn. For each player, the game will show 2 10x10 grids.
The top grid represents the current players target (i.e., the grid where the other player's ships reside), while the bottom represents the current player's ship deployment.At the start of the first player's first turn, the top grid will be completely empty, and the bottom grid will show only the location of the first player's ships.
On the bottom grid, each space occupied by part of an aircraft carrier will contain an "A", each space occupied by part of a battleship will contain a "B", each space occupied by part of a submarine will contain an "S".    

The player is then free to click a space into top grid to "fire" at. Clicks on the lower grid will have no effect.
The game will pop up an alert to inform the player whether the shot was a hit or a miss.
If the player clicks on a space where no part of any of the other player's ships was placed, the shot is a miss, and the space will be colored white. If some part of one of the other player's ships was placed in the clicked space, the shot is a hit, and the space should be will be colored red. If this hit represents the final portion of a ship (i.e., the 5th hit on an aircraft carrier, the 4th hit on a battleship, or the 3rd hit on a submarine), the player will be alerted as to which of the other player's ships they have sunk.  

At any point in time, a player's top grid will display all the hits(red spaces) and misses (white spaces) that they have fired, while the bottom grid will show all of the hits and misses their opponents have fired along with their ship placements.  

The game continues until all of one player's ships have been sunk, at which point the other player wins the game.
Once a winner has been established, the game computes the winner's score:  
Score is computed as: 24 - (2 points for each hit against them)  
10 points for sinking the opponent's aircraft carrier  
8 points for sinking the opponent's battleship  
6 points for sinking the opponent's submarine  
If Alice won the game while Bob was able to sink her submarine and land a single hit on her battle ship, but did not hit her aircraft carrier at all, Alice score would be 16: 24 - (2 * 4)  

The game keeps track of the names and scores of the 10 players with the highest scores in local storage.  

The game does not persist across page refreshes. A page refresh will restart the game.
