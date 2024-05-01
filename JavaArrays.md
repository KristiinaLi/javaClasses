## JavaArrays

```java
import java.util.Scanner;

/*
int number = 5;
int number2 = 7;
int number3 = 9;
System.out.println(number);
System.out.println(number2);
System.out.println(number3);
*/

public class Main {
  public static void main(String[] args) {

    int[] arr = {5, 7, 9};
    
    System.out.println(arr[0]);
    System.out.println(arr[1]);
    System.out.println(arr[2]);

    int[] arr2 = new int[5]; // Creats a new array with 5 elements
    arr2[0] = 5;
    arr2[1] = 7;
    arr2[2] = 9;
    arr2[3] = 12;
    arr2[4] = 15;

    for(int i= 0; i < arr2.length; i++){
      System.out.println(arr2[i]);
    } 
  }
}
```

```java
Scanner scanner = new Scanner(System.in);
    
    int[] arr2 = new int[5]; // Creates a new array with 5 elements
    arr2[0] = scanner.nextInt();
    arr2[1] = scanner.nextInt();
    arr2[2] = scanner.nextInt();
    arr2[3] = scanner.nextInt();
    arr2[4] = scanner.nextInt();

    for(int i= 0; i < arr2.length; i++){ //[0], [1], [2]
      System.out.println(arr2[i]);
```

```java
import java.util.Scanner;

/*
int number = 5;
int number2 = 7;
int number3 = 9;
System.out.println(number);
System.out.println(number2);
System.out.println(number3);
*/

public class Main {
  public static void main(String[] args) {

    int[] arr = {5, 7, 9};
    
    System.out.println(arr[0]);
    System.out.println(arr[1]);
    System.out.println(arr[2]);

    Scanner scanner = new Scanner(System.in);
    
    int[] arr2 = new int[5]; // Creats a new array with 5 elements; bounds are 0 to 4.
    arr2[0] = scanner.nextInt();
    arr2[1] = scanner.nextInt();
    arr2[2] = scanner.nextInt();
    arr2[3] = scanner.nextInt();
    arr2[4] = scanner.nextInt();

    for(int i= 0; i < arr2.length; i++){
      System.out.println(arr2[i]);
    }
    scanner.close();
   }
}
```

```java

public class Main {
  public static void main(String[] args) {

    int[] numbers = new int[5]; // int[] numbers = {1, 7, 3, -2, 100};
    numbers[0] = 1;
    numbers[1] = 7;
    numbers[2] = 3;
    numbers[3] = -2;
    numbers[4] = 100;

    int maxNumber = numbers[0]; 
    /* 1 > 1 ... 7 > 1 ... 7 > 3 ... 7 > -2 ... 7 < 100 ... maxNumber is 100 
      */
    
    for (int i = 0; i < numbers.length; i++){
      if (numbers[i] > maxNumber){
        maxNumber = numbers[i]; // overwriting max number value
      }
    }
      System.out.println("Max value here is: " + maxNumber); 
  }
}
```

```java
/*

We have an array with different numbers {1, 3, 4, 2, 5, 8}

User is providing a number

Check whether or not this number exists in the array
*/

import java.util.Scanner;

public class Main {
  public static void main(String[] args) {

    int[] numbers = { 1, 3, 4, 2, 5, 8 }; // numbers.length = size of the numbers = 6

    System.out.println("Please write your favourite digit");

    Scanner scanner = new Scanner(System.in);
    int favouriteNumber = scanner.nextInt();

    boolean isFound = false;
    
    for (int i = 0; i < numbers.length; i++) {

      if (numbers[i] == favouriteNumber) {
        isFound = true;
        break; //EXITS THE FOR LOOP ALTOGETHER, ignoring the i < numbers.length
      }
      
    }
    if(isFound){
      System.out.println("Your favourite number " + favouriteNumber + " is in the array");
    } else {
      System.out.println("Your favourite number " + favouriteNumber + " is NOT FOUND!");
    }
    
    scanner.close();
  }
}
```

```Java
/* 
Array with different numbers 
  User provides a number
  Check whether or not the input is in the array
  */
import java.util.Scanner;


public class Main {
  public static void main(String[] args) {
     int[] numbers = {1, 2, 3, 4, 5, 8};

    Scanner scanner = new Scanner(System.in);
    System.out.print("Enter your favourite digit: ");
    int favouriteNumber = scanner.nextInt();

    boolean isFound = false;

    for (int i = 0; i < numbers.length; i++) {
      if (numbers[i] == favouriteNumber) {
        isFound = true;
        break; // exits the for loop all together, ignoring the i<numbers.length
      }
      
    }
    if(isFound){
      System.out.println("Your favourite number" + favouriteNumber + "is in the array.");
    }
      else{
        System.out.println("Your favourite number" + favouriteNumber + "is NOT FOUND.");
      }
    
    scanner.close();  
  }
}
```

## Group work Ieva's Christmas card

```java
import java.util.Scanner;
import java.lang.Math;

public class Main {
  public static void main(String[] args) {
    Scanner input = new Scanner(System.in);
    System.out.print("Enter the number of random integers (-100 to 100) in the array: ");
    int n = input.nextInt();
    int[] arr = new int[n];
    System.out.print("Guess a number (-100 to 100): ");
    int guess = input.nextInt();
    System.out.println("The elements of the array are:");
    System.out.print("{ ");
// assigning random values to the array and printing them
    for(int i = 0; i < n; i++) {
      arr[i] = (int)(Math.random() * 201 -100);
      System.out.print(arr[i]);
      if (i < n - 1) {
        System.out.print(", ");
      }
    }
        System.out.println(" }");

    int maxVal = arr[0];
    int minVal = arr[0];
    int sum = 0;
    int indMax = 0;
    int indMin = 0;
    int indGuess = -1;

     System.out.println("The NEGATIVE elements of the array are:");
        System.out.print("{ ");

        // finding the negative elements
        for(int i = 0; i < n; i++) {
          if (arr[i] < 0) {
            System.out.print(arr[i]);
            if (i < n - 1) {
              System.out.print(", ");
            }
          }
        }
            System.out.println(" }");

        // finding the max, the min and the sum of elements
        for(int i = 0; i < arr.length; i++){ 
          sum += arr[i];
          if (arr[i] > maxVal) {
            maxVal = Math.max(maxVal, arr[i]);
            indMax = i;
          }
          if (arr[i] < minVal) {
            minVal = Math.min(maxVal, arr[i]);
            indMin = i;
          }
        // checking whether or not the guess is in the array
          if (arr[i] == guess) {
            indGuess = i;
          }
        }
          //checking for the second highest element
          int secondMax = arr[0];
          for(int i = 0; i < arr.length; i++) { 
            if (i != indMax) {
              if (arr[i] > secondMax) {
                secondMax = arr[i];
              }
            }
          }

        //printing the results of the calculations
          System.out.println("The largest value in the array is: " + maxVal + " situated at index: " + indMax);
        System.out.println("The second largest value in the array is: " + secondMax + ", so the largest sum of two elements is: " + (maxVal + secondMax));
          System.out.println("The smallest value in the array is: " + minVal + " situated at index: " + indMin);
        if (indGuess != -1) {
          System.out.println("The value " + guess + " is in the array at index: " + indGuess);
        } else {
          System.out.println("The value " + guess + " is not in the array");
        }
        System.out.println("The sum of all elements in the array is: " + sum);
      }
    }
```
## Group work 1 
/* Easy: Fill the array with random numbers

Find the sum of all elements in the array. For example in an array like this: [2, 3, 5, 1] Result: 11 (2 + 3 + 5 + 1) */

```java
public class Main {
  public static void main(String[] args) {
    int[] numbers = {1, 24, 53, 73, 84, 5, 8, 10};
    int sum = 0;

    for (int i = 0; i < numbers.length; i++){
      sum += numbers[i];
    }
    System.out.println(sum);
  }
}
```

## Group work 2
/* Find all the elements in the array that is below 0 [-2, 3, -5, 1] Result: -2 -5 */

```java
public class Main {
  public static void main(String[] args) {
    int[] array = {-2, 3, -5, 1};

      for (int i = 0; i < array.length; i++) {
        if (array[i] < 0) {
          System.out.println(array[i]);
        }
      }
  }
}
```

## Group work 3 - on my own
/*
Fill the party list with people you would like to invite to the party.
Check whether or not "Anna" is in the array.
Check whether or not "Maris" is in the array.
["Oskars", "Anna", "Andris"]
Result: 
"Anna is in the party list"
"Maris is not in the party list"
*/

```java
public class Main {
  public static void main(String[] args) {
    String[] partyList = {"Oskars", "Anna", "Andris"};
    boolean annaFound = false;
    boolean marisFound = false;
    
    for (String name : partyList) {
      if (name.equals("Anna")) {
        annaFound = true;
      }
      if (name.equals("Maris")) {
        marisFound = true;
      }
      }
      if (annaFound) {
        System.out.println("Anna is in the party list");
          }
        else {
          System.out.println("Anna is not in the party list");
        }
      if (marisFound)
          System.out.println("Maris is not in the party list");
        else {
          System.out.println("Maris is not in the party list");
        }
        }
  }
  ```

## Group work 3 with the help of chatGPT
/* Fill the party list with people you would like to invite to the party. Check whether or not "Anna" is in the array. Check whether or not "Maris" is in the array. ["Oskars", "Anna", "Andris"] Result: "Anna is in the party list" "Maris is not in the party list" */

```java
public class Main {
  public static void main(String[] args) {
    String[] partyList = {"Oskars", "Anna", "Andris"};
    String[] namesToCheck = {"Anna", "Maris"};

    for (String name : namesToCheck){
      boolean found = false;

      for (String partyPerson : partyList){
        if (partyPerson.equals(name)){
          found = true;
          break;
        } 
      }
      if (found){
        System.out.println(name + " is in the party list");
      } else {
        System.out.println(name + " is not in the party list");
        }
      }
    }
  }
```

## Group work 3 Oskar's version
/*
3. 
Fill the party list with people you would like to invite to the party.
Check whether or not "Anna" is in the array.
Check whether or not "Maris" is in the array.
["Oskars", "Anna", "Andris"]
Result: 
"Anna is in the party list"
"Maris is not in the party list"

Oscar's version
*/

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
    
    String[] partyList = {"Oskars", "Anna", "Andris"};

    Scanner scanner = new Scanner(System.in);
    String name = scanner.nextLine();

    boolean isInvited = false; // needed to check whether the person is not on the list; We make an assumption that the person is not on the list when we start the loop.
    
    for (int i = 0; i < partyList.length; i++){
      if (partyList[i].equals(name)){
        isInvited = true; // If the person is on the list, we change the value of isInvited to true and return this information.
        System.out.println(name + " is invited");
        break; // We break the loop as soon as we find the person.
      }
    }

    if(!isInvited){
      System.out.println(name + " is not invited");
    }
  }
}
```

## Group work 4
/* Difficult: Given an array of integers, write a Java program to find the maximum sum of two integers in the array.

For example in an array like this: [2, 3, 1, 5, 4] The maximum sum would be 5 + 4 */

```java
public class Main {
  public static void main(String[] args) {
    int[] array = {2, 3, 1, 5, 4};
    int max = array[0];
    int secondMax = array[0];

    for (int i = 0; i < array.length; i++) {
      if (array[i] > max) {
        max = array[i];
        
      }
      if (array[i] != max){
        secondMax = array[i];
      }
      }
    int sum = max + secondMax;
    System.out.println("Maximum number in this array is: " + max);
    System.out.println("Second largest number in this array is: " + secondMax);
    System.out.println("The sum of those numbers is: " + sum);
  } 
}
```
