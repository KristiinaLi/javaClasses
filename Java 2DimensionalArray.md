## 2 Dimensional Arrays

// Two dimensional arrays
/*
data_type[][] array_name = {
   {valueR1C1, valueR1C2, ....}, 
   {valueR2C1, valueR2C2, ....}
 };
*/

```java
public class Main {
  public static void main(String[] args) {
    int[] oneDimensionalArray = {1, 2, 3}; // Commas between values
    int[][] array = { // commas between arrays
      {1, 2, 3}, 
      {4, 5, 6},  
      {7, 8, 9}
  };
    for(int i = 0; i < oneDimensionalArray.length; i++){
      System.out.print(oneDimensionalArray[i]);
    }
    for(int i = 0; i < array.length; i++){
      for(int j = 0; j < array[i].length; j++){
        System.out.print(array[i][j]);
      }
    }
  }
}
```

```java
public class Main {
  public static void main(String[] args) {
    int[] oneDimensionalArray = {1, 2, 3}; // Commas between values
    int[][] array = { // commas between arrays
      {1, 2, 3}, 
      {4, 5, 6},  
      {7, 8, 9}
  };
    for(int i = 0; i < array.length; i++){
      int[] row = array[i];
      for(int j = 0; j < row.length; j++){ // Processing the rows here
        System.out.print(row[j] + "_" + "|"); 
      }
      System.out.println();
    }
  }
}
```

## Defined by 1
```java
public class Main {
  public static void main(String[] args) {
    int[][] array = new int[5][5];
    
    for(int i = 0; i < array.length; i++){
      int[] row = array[i];
      for(int j = 0; j < row.length; j++){ 
        row[j] = 1;
      }
    }
    for(int i = 0; i < array.length; i++){
      for(int j = 0; j < array[i].length; j++){
         System.out.print(array[i][j] + "|");
      }
      System.out.println();
      System.out.println("----------");
    }
  }
}
```

## Defined by "i"
```java
public class Main {
  public static void main(String[] args) {
    int[][] array = new int[5][5];
    
    for(int i = 0; i < array.length; i++){
      int[] row = array[i];
      for(int j = 0; j < row.length; j++){ 
        row[j] = i;
      }
    }
    for(int i = 0; i < array.length; i++){
      for(int j = 0; j < array[i].length; j++){
         System.out.print(array[i][j] + "|");
      }
      System.out.println();
      System.out.println("----------");
    }
  }
}
```

## Defined by "j"
```java
public class Main {
  public static void main(String[] args) {
    int[][] array = new int[5][5];
    
    for(int i = 0; i < array.length; i++){
      int[] row = array[i];
      for(int j = 0; j < row.length; j++){ 
        row[j] = j;
      }
    }
    for(int i = 0; i < array.length; i++){
      for(int j = 0; j < array[i].length; j++){
         System.out.print(array[i][j] + "|");
      }
      System.out.println();
      System.out.println("----------");
    }
  }
}
```

## Multiplication table
```java
public class Main {
    public static void main(String[] args) {
        int[][] array = new int[10][10];

        for (int i = 0; i < array.length; i++) {
            int[] row = array[i];
            for (int j = 0; j < row.length; j++) {
                row[j] = i*j;
            }
        }

        for(int i = 0; i < array.length; i++){
            for(int j = 0; j < array[i].length; j++){
                if(array[i][j] < 10){
                    System.out.print(array[i][j] + "  ");
                }
                else{
                    System.out.print(array[i][j] + " ");
                }
            }
            System.out.println();
        }
    }
}
```

## First column, every second row
```java
public class Main {
  public static void main(String[] args) {
    int[][] array = new int [5][5];
   
    for(int i = 0; i < array.length; i++){
    int[] row = array[i];
      for(int j = 0; j < row.length; j++){ 
        row[j] = 1;
        i = i + 1;
        j = j + 5;
      }
    }
    for(int i = 0; i < array.length; i++){
      for(int j = 0; j < array[i].length; j++){
        System.out.print(array[i][j] + " ");
      }
    System.out.println();
    }
  }
}
```

## Fill in the 5x5 array
## AI option
/*
Easy: 
Fill the 5x5 array with numbers from 1 to 25
1 2 3 4 5
6 7 8 9 10
...
But you have to use for loop to fill it up automatically.

```java
public class Main {
  public static void main(String[] args) {
    int[][] array = new int [5][5];
   
    for(int i = 0; i < array.length; i++){
    int[] row = array[i];
      for(int j = 0; j < row.length; j++){ 
        row[j] = (i * 5) + j + 1;
      }
    }
    for(int i = 0; i < array.length; i++){
      for(int j = 0; j < array[i].length; j++){
        System.out.print(array[i][j] + "   ");
      }
    System.out.println();
    }
  }
}
```

## Better option
```java
public class Main {
  public static void main(String[] args) {
    int[][] array = new int [5][5];
    int number = 1;
   
    for(int i = 0; i < array.length; i++){
      for(int j = 0; j < array[i].length; j++){ 
        if(number < 10){
          System.out.print(" " + number + " ");
        }else{
          System.out.print(number + " ");
      }
    number = number + 1;
    }
    System.out.println();
    }
  }
}
```

## Reference type vs value type

## Number
```java
public class Main {
  public static void main(String[] args) {
    int number = 20; // Reference type
    number = changeNumber(number);
    System.out.println(number);
    int numberVoid = 20; // Value type
    changeNumberVoid(numberVoid);
    System.out.println(numberVoid);
  }
  
  public static int changeNumber(int number){
    number = 55;
    return number;
  }

  public static void changeNumberVoid(int number){
    number = 55; // This number will not change the numberVoid value.   
  }
}
```
## array
```java
public class Main {
    public static void main(String[] args) { // Main method
      int[] array = {1, 2, 3, 4, 5}; //1. Declare an array 
      array = changeArray(array); //2. change the content of the array
      printOutArray(array); //3. print out the values of the array
    }
  
    public static int[] changeArray(int[] array) { // 2
      for(int i = 0; i< array.length; i++){ // 2.1
        array[i] = 0; // 2.2
      } // 2.3
      return array; // 2.4
    }
  
    public static void printOutArray(int[] array){ // 3
      for(int i = 0; i< array.length; i++){ //3.1
        System.out.println(array[i]); // 3.2
      } // 3.3
    }  
}
```

## Minesweeper

```java
public class Main {
    public static void main(String[] args) { // Main method
        int size = 10;
        int[][] grid = new int[size][size];
        int bombColumn = 9;
        int bombRow = 1;
        // 1 1 1 0 0 0 0 0 0 0
        // 1 5 1 0 0 0 0 0 0 0
        // 1 1 1 0 0 0 0 0 0 0
        // 0 0 0 0 0 0 0 0 0 0
        // .... times 10

        grid[bombRow][bombColumn] = 5; // Center
        if(bombRow != 0) {
            grid[bombRow - 1][bombColumn] = 1; // Top middle

            if(bombColumn != 0){
                grid[bombRow - 1][bombColumn - 1] = 1; // top left
            }

            if(bombColumn != size - 1){
                grid[bombRow - 1][bombColumn + 1] = 1; // top right
            }
        }

        if(bombRow != size - 1){
            grid[bombRow + 1][bombColumn] = 1; // bottom middle
            if(bombColumn != 0){
                grid[bombRow + 1][bombColumn - 1] = 1; //bottom left
            }
            if(bombColumn != size - 1){
                grid[bombRow + 1][bombColumn + 1] = 1; //bottom right
            } 
        }

        if(bombColumn != 0){
            grid[bombRow][bombColumn - 1] = 1; // middle left
        }
        if(bombColumn != size - 1){
            grid[bombRow][bombColumn + 1] = 1; //middle right
        }
        
        printArray(grid, size);
    }

    public static void printArray(int[][] array, int size) {
        for (int i = 0; i < size; i++) {
            for (int j = 0; j < size; j++) {
                System.out.print(array[i][j] + " ");
            }
            System.out.println();
        }
    }
}
```



