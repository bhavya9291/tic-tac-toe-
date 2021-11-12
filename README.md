# tic-tac-toe-
we developed a positional game using java 
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
