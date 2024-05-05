# Java-Loops
Loops

## 1

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {

   System.out.println("Hello world!");

// if (true) { //Do action }

  int amoutOfTimesToDuck = 10;
    while (amoutOfTimesToDuck != 0) {
      System.out.println("Duck");
      amoutOfTimesToDuck = amoutOfTimesToDuck - 1;
```

## 2

```java
public class Main {
  public static void main(String[] args) {
    
    System.out.println("Hello world!");

    int amountOfTimesToDuck = 10;
    while (amountOfTimesToDuck != 0) {
      System.out.println(amountOfTimesToDuck);
      amountOfTimesToDuck = amountOfTimesToDuck - 1;
    }
    
  }
}
```

## 3
int repetitions = 1;  // Duck 10 times!

    while(repetitions < 11){  // Count UP!
      System.out.println("Duck! Counter: " + repetitions);
      repetitions = repetitions + 1;
    }

## 4

        int i = 0;

        while (i < 10) {
          System.out.println(i);
          i = i + 1;
        }
## 5

```java

import java.util.Scanner;

public class Main {
  public static void main(String[] args) {


// if (true) { //Do action }

        int i = 1;
        boolean isEven = false;
        // Counts from 0 to 10
        // Provides whether or not the number is even or odd
    
        while (i <= 10) {
          String evenOrOdd = "";
          if (isEven == true) {
            evenOrOdd = "even";
         }else{
            evenOrOdd = "odd";
         }
          System.out.println(i + " " + evenOrOdd);
          i = i + 1;
          isEven = !isEven;
        }
      
    //scanner.nextLine(); // Waits for us to provide a string until pressed enter 
      }}
```

## 6

```java

import java.util.Scanner;

public class Main {
  public static void main(String[] args) {


// if (true) { //Do action }


        int i = 1; // First number is always 1
        boolean isEven = false; // First number is always ODD
        // isEven is True for second number
        // Counts from 0 to 10
        // Provides whether or not the number is even or odd
    
        while (i <= 10) {
          String result = "";
          if (isEven == true) {
            result = "even";
         } else {
            result = "odd";
         }
          System.out.println(i + " " + result);
          i = i + 1;
          isEven = !isEven;
          // isEven == true --> isEven = false
          // isEven == false
        }
    
  

    //scanner.nextLine(); // Waits for us to provide a string until pressed enter 
      }}
```

## 7

```java
public class Main {
  public static void main(String[] args) {

    System.out.println("Hello world!");

    int i = 1; // 1
          //1 <= 10 -> TRUE
          //2 <= 10 -> TRUE
          //3 <= 10 -> TRUE
          //...
          //11 <= 10 -> FALSE
    while (i <= 10) {
      String result = ""; // Result
      if (i % 2 == 0) { //Odd or even
        result = "even";
      } else {
        result = "odd";
      }
                        //1 odd
                        //2 even
      System.out.println(i + " " + result);
      i = i + 1; // i = i + 1;
      //i = 1 + 1;
      //i = 2 + 1;
      //i = 3 + 1;
    }
  }
}
```

## 8

public class Main {
  public static void main(String[] args) {
    int i = 1;
    while (i <= 10) {
      // Start action

      System.out.println(i);
      // End action
      i = i + 1;
    }
  }
}

## WHILE LOOP
 int i = 1;
    while (i <= 10) {
      // Start action

      System.out.println(i);
      // End action
      i = i + 1;
    }

// while loop is more suitable for true or false conditions; whereas for loop is more for situations where you already know the exact amount.
// The while loop is typically used when you need to repeatedly execute a block of code until a specific condition becomes false or true.

## FOR LOOP

for (int i = 1 i <= 10; i = i + 1){
      System.out.println(i);
    }
//The for loop is typically used when you know the exact number of iterations/loops or when you need to iterate over a range of values.


## GROUP WORK

### 1. Create a triangle that is made of _ symbol
Ask the user for a number, and then print out x amount of lines, with "".
For example
if user writes 5, then _____, If user writes 3, then ___

```java

import java.util.Scanner;

public class Main {
  public static void main(String[] args) {

    Scanner scanner = new Scanner(System.in);
    
    System.out.println("Enter a number: ");
    int number = scanner.nextInt();
    
    String triangle = "_";
    for (int i = 1; i <= number; i++) {
      System.out.println(triangle);
      triangle = triangle + "_";
            
    }
    scanner.close();
  }
}
```

### 2. Guess a number inbetween 0 and 100
You can provide the user with information, whether or not the number is bigger or less than the guess

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {

    int randomNumber = (int) (Math.random() * 100);
      // System.out.println(randomNumber);

    Scanner scanner = new Scanner(System.in);
    
    System.out.println("Guess a number between 0 and 100");
    int guess = scanner.nextInt();
    int i = 1;

    while (guess != randomNumber) {
      if (guess > randomNumber) {
        System.out.println("Too high!");
      }
      else {
        System.out.println("Too low!");
      }
      System.out.println("Try again ");
      i++;  
            guess = scanner.nextInt();     
    }
    System.out.println("You guessed it in " + i + " times");
    
    scanner.close();
  }
}

```
## Triangle assignement with Oskars' comments

```java
import java.util.Scanner;
//1. Get user input x
//2. Create a for loop that runs x amount of times
//3. Inside the loop, print _ symbol i times

public class Main {
  public static void main(String[] args) {
    Scanner scanner = new Scanner(System.in); // Channel for input
    System.out.print("Enter a number: "); // User input
    int number = scanner.nextInt();
    
    String result = ""; // empty string
    for(int i = 1; i < number; i++) { 
      // i = 1 value added to a variable; 
      // i <= number - if this is true, then go on with the cycle;
      // i++ is the same as i = i + 1; i++ when you only want to add 1 to the variable; i = i + number when you want to add more than 1.
      // We do action before first cycle; condition for cycle; action after every cycle
      
      result = result + "_"; // result = "" + "_" = "_"; next time it will already be "_" + "_" = "__"; after that it will be "__" + "_" = "___"
      System.out.println(result);
    }
    scanner.close();
  }
```

## Opposite triangle
```java
import java.util.Scanner;
//1. Get user input x
//2. Create a for loop that runs x amount of times
//3. Inside the loop, print _ symbol i times

/*
    _
   __
  ___
 ____
_____  

// x = 5
// spaces = x -i
// underscores = i

*/
    
public class Main {
  public static void main(String[] args) {
    Scanner scanner = new Scanner(System.in);
    System.out.print("Enter a number: "); 
    int number = scanner.nextInt();
    
    String space = " ";
    String underScore = "_";
    
    for(int i = 10; i <= number; i++) { 
       int spacesCount = number - i;  
       String lineResult = space.repeat(spacesCount);
       String underScoreResult = underScore.repeat(i);
       lineResult = lineResult + underScoreResult;
           
      System.out.println(lineResult);
      }
```

## Guessing game with Oskars' comments; using break and continue

```java
    import java.util.Scanner;

    public class Main {
      public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);
        int number = 58;

        //1. We have a number

        //2. We ask for the user to guess the number
        //3. If the guessed number is bigger, then we say  "Too big"
        //4. If the guessed number is smaller, then we say "Too small"
        //5. If the guessed number is correct, then we say "Correct"
        //2-5 line a loop, we stop the loop, when the user is correct
        
        while(true) {
          System.out.println("Please guess a number!");
          int guess = scanner.nextInt(); //A number that user provides

          if (number == guess) {
            System.out.println("Good job, you guessed correctly");
            break;
          }
          if (number < guess) {
            System.out.println("Sorry, the number is too big!");
            continue;
          }
          System.out.println("Sorry, the number is too small!");
        }
        System.out.println("Guessing game is over!");
        scanner.close();
      }
    }
    scanner.close();
  }
}
```

## GROUP WORK
## 1
/*Team work: Develop a program, that iterates through numbers from 0 till X amount of times (X is user provided)
For numbers that are divided by 3: print out "Wo" .

For numbers that are divided by 5: print out "Tech". 

For numbers divided by 3 and 5: print out "WoTech".
  */

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
    Scanner scanner = new Scanner(System.in);

    System.out.print("Enter a number: ");
    int number = scanner.nextInt();
    
    String result = "";
    
    for (int i = 1; i <= number; i++) {
      
      if (i % 3 == 0 && i % 5 == 0) {
        result = "WoTech";
      } else if (i % 3 == 0) {
        result = "Wo";
      } else if (i % 5 == 0) {
        result = "Tech";
      } else {
        result = String.valueOf(i);
      }
    
      System.out.println(result);
    }
       
  }
}
```

## 2 User input string into a box
1. User writes a string --> calculate the width of the rectangle based on the number of characters in the string.
  1.a. RectangleWidth = WordLength + 3 x 2 + 1 x 2 
2. Sum of messageLength and padding and borders
  2.a. Padding is 3 characters long on one side
  2.b. Border is 1 character long on one side
3, Print out upper border ===========
4. Print out an empty line with border |
5. Print out the border + padding + message + padding + border |    message    |
6. Print out an empty line with border |
7. Print out lower border ===========

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {

    Scanner input = new Scanner(System.in);
    System.out.print("Enter a word:   ");
    String name = input.nextLine();
    System.out.print("How much space does your word need?  ");
    int spaceAround = input.nextInt();
    int lengthOfName = name.length();
    String line = "=";
    String space = " ";
    
    System.out.println("The name " + name + " has " + lengthOfName + " characters");

    String firstLine = line.repeat(lengthOfName + 2 * spaceAround + 2);
    String secondLine = "|" + space.repeat(lengthOfName + 2 * spaceAround) + "|";
    String thirdLine = "|" + space.repeat(spaceAround) + name + space.repeat(spaceAround) + "|";

    System.out.println(firstLine);
    System.out.println(secondLine);
    System.out.println(thirdLine);
    System.out.println(secondLine);
    System.out.println(firstLine);
    
  }
}
```

## Optimising code for "Wo" "Tech" "WoTech"
```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {

    Scanner scanner = new Scanner(System.in);
    System.out.println("Please enter a number: ");

    int number = scanner.nextInt(); //15

    for(int i = 1; i <= number; i++){
      // 1 2 3 4 5 ... 15
      String result = "";
      if(i % 3 == 0){ // 3 6 9 12 15
        result += "Wo";
      } 
      if(i % 5 == 0){ // 5 10 15 // if the first if is true, we still check the other if. With elif we would stop after the first true if. 
        result += "Tech";
      } 
      if(result.equals("")){ //if result is empty // almost the same as if(result == "")
        result = String.valueOf(i); //Then result = i (number)
      }
      System.out.println(result);

      scanner.close();
    }
  }
}
```

## Fill in the party list
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
