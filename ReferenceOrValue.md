## Reference type vs value type

```java
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
```

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

Reference type vs value type
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

## Group work 
// Reference type vs value type
//Easy: Create a copy of all primitive types (STRINGS INCLUDED)
//Hard: Create a copy of an array

```java
public class Main {
    public static void main(String[] args) { // Main method
      boolean isHuman = false;
      boolean isHuman2 = isHuman;
      isHuman2 = true;

      char char1 = 'a';
      char char2 = char1;
      char2 = 'b';

      System.out.println(char1);
      System.out.println(char2);

      int int1 = 1;
      int int2 = int1;
      int2 = 2;

      System.out.println(int1);
      System.out.println(int2);

      float f1 = 2.55f;
      float f2 = f1;
      f2 = 3.55f;

      System.out.println(f1);
      System.out.println(f2);

      double d1 = 3.14;
      double d2 = d1;
      d2 = 4.14;

      System.out.println(d1);
      System.out.println(d2);

      int [] arr1 = { 1, 2, 3, 4, 5, 6 };
      int [] arr2 = arr1;
      arr2[2] = 7;

      System.out.println(arr1[2]);

      String str1 = "abc";
      String str2 = str1;

      System.out.println(str1);
      System.out.println(str2);

      str2 = "def";
  ```
      
      System.out.print(str1);
      System.out.println(str2);     
      }  
    }
```
