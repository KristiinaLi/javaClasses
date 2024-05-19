## Tic Tac Toe game, single player

/*Create a simple tic-tac-toe game. Depending on your skills and knowledge.

Game grid should be 3x3. It should be possible for the user to put values in the grid by typing row number and column number.

Easy:
1. Create a 3 x 3 grid, initiate a two dimensional array.
2. Ask user for row and column and 
3. write in the two dimensional array a value "1" in the correct place.
4. Check whether or not the row chosen by user contains all 1.
5. If all elements in row contain 1, then let player know they've won.
*/

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
    int size = 3;
    int[][] grid = new int[size][size];
    printArray(grid, size);

    Scanner scanner = new Scanner(System.in);

    while (rowChecker(grid, size) == false && columnChecker(grid, size) == false && diagonalChecker(grid, size) == false) {
    System.out.println("Enter row number (1-3): ");
    int row = scanner.nextInt();
    System.out.println("Enter column number (1-3): ");
    int column = scanner.nextInt();
    grid[row - 1][column - 1] = 1;
    inputToIndex(grid, size, row, column);
    }

    if (rowChecker(grid, size) == true || columnChecker(grid, size) == true || diagonalChecker(grid, size)){
      System.out.println("You have won!");
    }
  }

  public static void printArray(int[][] grid, int size) {
    for (int i = 0; i < size; i++) {
      for (int j = 0; j < size; j++) {
         System.out.print(grid[i][j] + " ");
          }
    System.out.println();
    }
  }
  
  public static boolean rowChecker(int[][] grid, int size) {
    if (grid[0][0] == 1 && grid[0][1] == 1 && grid[0][2] == 1) {
      return true;
    }else if (grid[1][0] == 1 && grid[1][1] == 1 && grid [1][2] == 1){
      return true;
    }else if (grid[2][0] == 1 && grid[2][1] == 1 && grid [2][2] == 1){
      return true;
    }else{
      return false;
    }
  }

  public static boolean columnChecker(int[][] grid, int size){
    if (grid[0][0] == 1 && grid[1][0] == 1 && grid[2][0] == 1){                         
      return true;
    }else if (grid[0][1] == 1 && grid[1][1] == 1 && grid [2][1] == 1) {
      return true;
    }else if (grid[0][2] == 1 && grid[1][2] == 1 && grid[2][2] == 1) {
      return true;
    }else{
      return false;
    }
  }

  public static boolean diagonalChecker(int[][] grid, int size){
    if (grid[0][0] == 1 && grid[1][1] == 1 && grid[2][2] == 1){
      return true;
    }else if (grid[2][0] == 1 && grid[1][1] == 1 && grid [0][2] == 1) {
      return true;
    }else{
      return false;
    }
  }
  
  public static void inputToIndex(int[][] grid, int size, int row, int column) {
    if (row == 1 && column == 1) {
      grid[0][0] = 1;
      printArray(grid, size);
    }
    if (row == 1 && column == 2) {
      grid[0][1] = 1;
      printArray(grid, size);
    }
    if (row == 1 && column == 3) {
      grid[0][2] = 1;
      printArray(grid, size);
    }
    if (row == 2 && column == 1) {
      grid[1][0] = 1;
      printArray(grid, size);
    }
    if (row == 2 && column == 2) {
      grid[1][1] = 1;
      printArray(grid, size);
    }
    if (row == 2 && column == 3) {
      grid[1][2] = 1;
      printArray(grid, size);
    }
    if (row == 3 && column == 1) {
      grid[2][0] = 1;
      printArray(grid, size);
    }
    if (row == 3 && column == 2) {
      grid[2][1] = 1;
      printArray(grid, size);
    }
    if (row == 3 && column == 3) {
      grid[2][2] = 1;
      printArray(grid, size);
    }
    }
  }
```
