# 15.05.2024-Individual-Task-Java


/*
Create a simple tic-tac-toe game. Depending on your skills and knowledge.
Game grid should be 3x3. It should be possible for the user to put values in the grid by typing row number and column number.
Easy: Ask user for row and column and write in the two dimensional array a value "1" in the correct place.
Check whether or not the row chosen by user contains all 1.
If all elements in row contain 1, then let player know they won.
Medium: Ask for row and column and write in the two dimensional array a value "1" or "2" in the correct place, depending on which players turn it is. Switch the turn after every move.
Check whether or not the row chosen by user contains all 1, or all 2.
Check whether or not the column chosen by user contains all 1, or all 2.
(1 represents X, 2 represents O, 0 represents empty)
Hard: A regular tic-tac-toe, check diagonals as well. Instead of 1 and 0, use X and O (2D array should be of char type.)
After every move make sure the playing field is not full and make it draw, if it is full.
*/ 

import java.util.Scanner;

public class Main {
  public static void main(String[] args) {

     System.out.print("Welcome to Tic-Tac-Toe game! Game grid is 3x3. You can choose where to put your symbol. First who get three on a row - WINS the game.");
        System.out.println(); 
 
      int size = 3;
      char[][] grid = new char[size][size];
      initializeGrid(grid, size); //took from CHATGPT. Couldnt figure out bymyself
      Scanner scanner = new Scanner(System.in);

      boolean gameWon = false;
      boolean isXTurn = true;
      int moves = 0;

      while (!gameWon && moves < size * size) {
      printArray(grid, size);
      int row = enterRowAndColumn(scanner, "row");
      int column = enterRowAndColumn(scanner, "column");
    
          
      while (!addRowAndColumnInAGrid(grid, row, column));{
          System.out.println("This move is not valid. Try again.");
          row = enterRowAndColumn(scanner, "row");
          column = enterRowAndColumn(scanner, "column");
    } //while 2
      } //while 1

      
/* Missing
1 represents X, 2 represents O, 0 represents empty)
*/
      
  
scanner.close();
      
  } // closing main void 
    
   public static void initializeGrid(char[][] grid, int size) {
        for (int i = 0; i < size; i++) {
            for (int j = 0; j < size; j++) {
                grid[i][j] = '-';
            }
        }
    }
        public static void printArray(char[][] array, int size) {
        for (int i = 0; i < size; i++) {
            for (int j = 0; j < size; j++) {
                System.out.print(array[i][j] + " ");
            }
            System.out.println();
        }
    }
        public static int enterRowAndColumn(Scanner scanner, String coordinate) {
            System.out.print("Please enter a " + coordinate + " where to place a symbol (0-2): ");
             int number = scanner.nextInt();
             return number;
    }
  
         public static boolean addRowAndColumnInAGrid(char[][] grid, int row, int column) {
           return row >= 0 && row < 3 && column >= 0 && column < 3 && grid[row][column] == '-'; 
            }

    /* 
    Missing row, column, diagonal checks 
    */ 
        
   } // closing main 


    

  

       
  

        
  
      
  


