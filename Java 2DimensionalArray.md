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

## array with comments and extra method
```java
// Reference type vs value type

public class Main {
    public static void main(String[] args) { // Main method
      int[] array = { 1, 2, 3, 4, 5 }; //1. Declare an array 
      array = changeArray(array); //2. change the content of the array
      printOutArray(array); //3. print out the values of the array
      
      int[] arrayVoid = { 1, 2, 3, 4, 5 }; //4
      changeArrayVoid(arrayVoid); //5
      printOutArray(arrayVoid); //6
    }
  
   public static int[] changeArray(int[] array) { // 2
      for(int i = 0; i < array.length; i++) { // 2.1
        array[i] = 0; // 2.2
      } // 2.3
      return array; // 2.4 
    }
  
    public static void changeArrayVoid(int[] array) { // 3
      for(int i = 0; i < array.length; i++) { //3.1
        array[i] = 1; // 3.2
      } // 3.3
    }
  
    public static void printOutArray(int[] array) { // 5
       for(int i = 0; i < array.length; i++) { //5.1
         System.out.println(array[i]); // 5.2
        } // 5.3
      }  
    }

```

## Replacing an element
```java
public class Main {
    public static void main(String[] args) { // Main method
      int[] arrayVoid = { 1, 2, 3, 4, 5 };

      int[] array = arrayVoid;
      array[0] = 100;
      
      printOutArray(arrayVoid); 
    }
   
    public static void printOutArray(int[] array) {
       for(int i = 0; i < array.length; i++) {
         System.out.println(array[i]);
        }
      }  
    }
```

```java
public class Main {
    public static void main(String[] args) { // Main method
      int[] arrayVoid = { 1, 2, 3, 4, 5 };
      int[] array2 = new int[5];

      array2[0] = 1;
      array2[1] = 2;
      array2[2] = 3;
      array2[3] = 4;
      array2[4] = 5;

      System.out.println(arrayVoid == array2); // not comparing the values, but references.
      }  
    }

```java
public class Main {
    public static void main(String[] args) { // Main method
      int[] arrayVoid = { 1, 2, 3, 4, 5 };
      
      int[] array2 = arrayVoid;
      array2[0] = 123;
      System.out.println(arrayVoid == array2);
      System.out.println(arrayVoid[0]); // 123
      System.out.println(array2[0]); // 123     
      }  
    }
```
https://github.com/KristiinaLi/javaClasses/assets/165931675/9eeb635b-6a43-487a-9dc6-06a46365569a

![1__VfF_-1QHljCLERE0hSjsg](https://github.com/KristiinaLi/javaClasses/assets/165931675/5ab55043-b562-49c0-a36b-29f6aa34c8e5)

## Group work

// Reference type vs value type
// Easy: Create a copy of all primitive types (STRINGS INCLUDED)
// Hard: Create a copy of an array

## Reference Type
Shortcut of a Folder: When you create a shortcut to a folder, the shortcut points to the original folder. Any changes you make by accessing the folder through the shortcut affect the original folder.
In Java: A reference type variable points to an object. If you change the object using any reference to it, the change is reflected in all references.

## Reference Types
Objects and Arrays: These are always reference types. This includes:

Classes: Any instance of a class (e.g., String, ArrayList, user-defined classes).
Arrays: Even if they are arrays of primitive types (e.g., int[]).
These hold references to the objects or arrays, which are stored on the heap.

## Value Type
Copying a Folder: When you copy a folder, you get a new folder with the same contents. Any changes you make to the new folder do not affect the original folder.
In Java: A value type variable holds the actual value. When you copy a value type variable to another, you get a new copy of the value. Changes to the new copy do not affect the original value.

## Value Types
Primitive Data Types: These are always value types. Java has eight primitive data types:

byte
short
int
long
float
double
char
boolean
These hold their data directly and are stored on the stack.



