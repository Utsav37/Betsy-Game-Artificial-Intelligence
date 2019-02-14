# Betsy
Successors:
The successors are list of lists. eg. [[x_max],[y_max],[x_min],[y_min]] where x_max is the list of row indices of player 'x' ,
y_max is the list of column indices of player'x'.Similarly, x_min is the list of row indices of player 'o',y_min is the list of column indices of player'o'.

Note-I have used the constant 'max' for 'x' doesnt mean program considers 'x' as max all time. 
The variable "player" stands for the max player and the variable "opp" stands for the min player or the opponent

The result is that there are only n iterations for n successors i.e. the cost to generate a successor is only 1

We used this approach to prevent nxn iterations every time the program scans through the board
Problems faced-it was very difficult to tackle the index form of the board, although most function in the program does not take more than n iterations 
but it was hard to tackle the list of indices, considering I am a beginner in python.

Heuristic:
Given a board. In the first NxN grid find below:
1) take the minimum of below from the rows:
Calculate the number of pieces needed to win a row. Assign n*n*n as cost if cannot win.
2) take the minimum of below from the columns:
Calculate the number of pieces needed to win a column. Assign n*n*n as cost if cannot win.
3) take the minimum of below from the diagonals:
Calculate the number of pieces needed to win right diagonal. Assign n*n*n as cost if cannot win. 
Calculate the number of pieces needed to win left diagonal. Assign n*n*n as cost if cannot win

Heuristic for a board:
1)(Take the minimum of 1,2 and 3) + depth*0.1
2)Added depth*0.1 to take the depth into account in case the heuristic is same for leaf nodes at different depths. In which case the node at the lowest depth will be considered.
Used 0.1 so it does not affect the cost of nodes when they are different eg.3 will still be greater than 2.1 but not from 3(if 0.1 not multiplied)
3)
Note-Since we are using the index form its less costly to calculate this.
 
The important catch in minimax algorithm implemented is that we are minimising the cost i.e. the heuristic for the max player 
while min tries to maximise the  heuristic or the cost

Basically we are trying to minimize the cost for max player- hence the lesser the heuristic value returned the more favourable it is for max player
