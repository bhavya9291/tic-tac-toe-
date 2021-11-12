# tic-tac-toe
import java.util.Scanner; 

public class TICTACTOE2DARRAY { 

 

static Scanner in; 

static String[][] board; 

static String turn; 

 

public static void main(String[] args) { 

in = new Scanner(System.in); 

board = new String[3][3]; 

turn = "X"; 

String winner = null; 

 

 

 

populateEmptyBoard(); 

 

System.out.println("Welcome to 2 Player Tic Tac Toe."); 

System.out.println("--------------------------------"); 

printBoard(); 

System.out.println("X's will play first. Enter a slot number to place X in:"); 

 

while (winner == null) { 

int numInput; 

int val1=0,val2=0; 

String flag= "false"; 

 

numInput = in.nextInt();  

if (!(numInput > 0 && numInput <= 9)) { 

System.out.println("Invalid input; re-enter slot number:"); 

continue; 

} 

 

for (int i = 0; i < 3; i++) { 

for (int j = 0; j < 3; j++) { 

//System.out.println("board[i][j]"+board[i][j]); 

//System.out.println(String.valueOf(numInput)); 

if (board[i][j].equals(String.valueOf(numInput)))				 

{ 

//System.out.println("board[i][j]"+board[i][j]); 

val1 =i; 

val2 =j; 

flag = "TRUE"; 

} 

} 

} 

if (flag == "TRUE") 

{							 

board[val1][val2] = turn; 

if (turn.equals("X")) { 

turn = "O"; 

} else { 

turn = "X"; 

} 

printBoard(); 

winner = checkWinner(); 

}  

 else if(flag == "false") { 

System.out.println("Slot already taken; re-enter slot number:"); 

continue; 

} 

} 

if (winner.equalsIgnoreCase("draw")) { 

System.out.println("It's a draw! Thanks for playing."); 

} else { 

System.out.println("Congratulations! " + winner + "'s have won! Thanks for playing."); 

} 

} 

 

static String checkWinner() { 

for (int a = 0; a < 8; a++) { 

String line = null; 

switch (a) { 

case 0: 

line = board[0][0] + board[0][1] + board[0][2]; 

break; 

case 1: 

line = board[1][0] + board[1][1] + board[1][2]; 

break; 

case 2: 

line = board[2][0] + board[2][1] + board[2][2]; 

break; 

case 3: 

line = board[0][0] + board[1][0] + board[2][0]; 

break; 

case 4: 

line = board[0][1] + board[1][1] + board[2][1]; 

break; 

case 5: 

line = board[0][2] + board[1][2] + board[2][2]; 

break; 

case 6: 

line = board[0][0] + board[1][1] + board[2][2]; 

break; 

case 7: 

line = board[0][2] + board[1][1] + board[2][0]; 

break; 

} 

if (line.equals("XXX")) { 

return "X"; 

} else if (line.equals("OOO")) { 

return "O"; 

} 

} 

String flag1= "false"; 

for (int a = 0; a < 9; a++) { 

for (int i = 0; i < 3; i++) { 

for (int j = 0; j < 3; j++) { 

//System.out.println("board[i][j]"+board[i][j]); 

//System.out.println(String.valueOf(a+1)); 

if (String.valueOf(board[i][j]).equals(String.valueOf(a+1)))				 

{ 

flag1 = "TRUE"; 

//System.out.println("Hello"); 

//System.out.println("board[i][j]"+board[i][j]); 

} 

  else if (flag1=="false" && (a == 8) ) return "draw"; 

} 

} 

} 

 

System.out.println(turn + "'s turn; enter a slot number to place " + turn + " in:"); 

return null; 

} 

 

static void printBoard() { 

System.out.println("/---|---|---\\"); 

System.out.println("| " + board[0][0] + " | " + board[0][1] + " | " + board[0][2] + " |"); 

System.out.println("|-----------|"); 

System.out.println("| " + board[1][0] + " | " + board[1][1] + " | " + board[1][2] + " |"); 

System.out.println("|-----------|"); 

System.out.println("| " + board[2][0] + " | " + board[2][1] + " | " + board[2][2] + " |"); 

System.out.println("/---|---|---\\"); 

} 

 

static void populateEmptyBoard() { 

int count=0; 

for (int i = 0; i < 3; i++) { 

for (int j = 0; j < 3; j++) 

board[i][j] = String.valueOf(++count); 

} 

} 

}


 

