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

