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


