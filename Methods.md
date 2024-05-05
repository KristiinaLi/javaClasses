## METHODS

// METHODS == Function

// After every input, it prints out a line =========
// We can create a method, that creates this for us if we want something to be repeated multiple times. 

// I might want to add my own custom method
// I can do that by adding a new method
// I don't have to add it, but I can
// What happens in Vegas, stays in Vegas = What happens in this method, stays in this method. 
// Other methods don't see what's going on in there. 
// If you define a scanner in one method, it can't be used in another method.
// In order to share a scanner between methods, you have to declare it in class, before the first method.

```java
public class Main { // capital Main is a class name, and lowercase main is a method name
  public static void main(String[] args) {
    printLine(); // using the method

    System.out.println("Hello world!");
    int number = getARandomNumber();
    System.out.println(number);
    printLine();
  }
  public static void printLine() {  // creating a method; curly brackets start and end the method.
    System.out.println("=================");
  }
```

/* Access modifiers: Private, protected and public - private cannot be accessed outside of the class, public can be accessed outside of the class. Always use public. Relevant when we talk about object oriented programming. */

/*  Whether or not the function is static: static or nothing - static means that the method belongs to the class, not to an object. Becomes relevant when we talk about object oriented programming. Always use static */

/* Return type: Void - void means that the method does not return anything. Just an action. Determines what kind of a function is returned. We can use any data type here (int, boolean, string. */

/* This code is not linear, it takes things from lower down, and uses thoses things to create the next thing in the first part. */

```java
public static int getARandomNumber() {
  return 5;
}
}
```

```java
public class Main {
  public static void main(String[] args) {

    int number1 = 5;
    int number2 = 7;
    int result = sum(number1, number2);
    System.out.println(result);
  }

  public static int sum (int number1, int number2) {
    return number1 + number2;
  }
}
```

## Did the same on my own

```java
/*
Easy:

Sum of 2 numbers
User provides 2 numbers
Result is a sum of those numbers

Example: 
User inputs 5
User inputs 6
Result: 11
  */

import java.util.Scanner;
  
public class Main {
  public static void main(String[] args) {
    Scanner scanner = new Scanner(System.in);
    System.out.println("Enter a number");
    int number1 = scanner.nextInt();
    scanner.nextLine();
    System.out.println("Enter another number");
    int number2 = scanner.nextInt();
    scanner.nextLine();

    int result = sum(number1, number2);
    System.out.println("The sum of " + number1 + " and " + number2 + " is " + result);

    scanner.close();
  }
    
    public static int sum (int a, int b){
    return a + b;
  }
}
```

## IS THE SAME AS
```java
public class Main {
  
  public static void main(String[] args) {
    int number1 = 5;
    int number2 = 7;
    int result = number1 + number2;
    System.out.println(result);
  }
}
```

```java
/*
Write a name and check whether or not it is atleast 3 char long
   Write a surname and check whether or not it is atleast 3 char long
If it's not, then say. Sorry, your name is too short.
If both of them are valid, say. Thank you, your information has been registered!
  */

public class Main {
  public static void main(String[] args) {
    String name = "Oskars";
    String surname = "Klaumanis";
    boolean isUserNameValid = isNameValid(name); // Give the function "Oskars" as an argument.
    // Because "Oskars" is longer than 3, isUserNameValid = true;
    
    boolean isUserSurnameValid = isNameValid(surname); // Give the function "Klaumanis" as an argument
    // Because "Klaumanis" is longer than 3, isUserNameValid = true;

    if(isUserNameValid && isUserSurnameValid){
      System.out.println("Thank you, your information has been registered!");
    }else{
      System.out.println("Sorry, your name is too short.");
    }
    }
  
public static boolean isNameValid(String name) { //name == "Oskars"
  if(name.length() < 3){ // CHecking whether the name is atleast 3 char long
    System.out.println("Sorry, your name is too short.");
    return false;
  }
return true; // Beccause "Oskars" length is more than 3, we return true.
 }
  }
```

## GROUP WORK
## EASY
/*
Easy:

Sum of 2 numbers
User provides 2 numbers
Result is a sum of those numbers

Example: 
User inputs 5
User inputs 6
Result: 11
*/

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
    Scanner scanner = new Scanner(System.in);

    System.out.println("Enter the first number: ");
    int firstNumber = scanner.nextInt();
    scanner.nextLine();
    System.out.println("Enter the second number: ");
    int secondNumber = scanner.nextInt();
    scanner.nextLine();

    int result = sum(firstNumber, secondNumber);
    System.out.println("The sum of " + firstNumber + " and " + secondNumber + " is " + result);
    
    scanner.close();
  }
  public static int sum(int firstNumber, int secondNumber){
    return firstNumber + secondNumber;
  }
}
```

## Difficult - with the help of ChatGPT

/*Hard:
1. Create a program, where user can provide a title and a small text below the story.
Title should be wrapped with ====== at top and bottom, based on the title length.
Example: 
System asks for title and user provides "WoTech and Java is easy"
System asks for description and user provides "I have been learning Java for 6 weeks now."

Result: 
=======================
WoTech and Java is easy
=======================

I have been learning Java for 6 weeks now.

Plan: 
1. Import scanner
2. Ask for title
3. Ask for description
4. Create a method that will wrap the title
5. Print out wrapped title
6. Print out description
*/

```java
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
    Scanner scanner = new Scanner(System.in);
    
    System.out.println("Enter a title: ");
    String title = scanner.nextLine();
    System.out.println("Enter a description: ");
    String description = scanner.nextLine();

    printTitle(title);
    System.out.println(description); 

    scanner.close();
  }
public static void printTitle(String title){
  int length = title.length();
StringBuilder line = new StringBuilder(); // This is the part I got help from Chat GPT

  for(int i = 0; i < length; i++){
    line.append("=");
  }
  System.out.println(line);
  System.out.println(title);
  System.out.println(line);
}
}
```

## Finally figured out another way

/*Hard:
1. Create a program, where user can provide a title and a small text below the story.
Title should be wrapped with ====== at top and bottom, based on the title length.
Example: 
System asks for title and user provides "WoTech and Java is easy"
System asks for description and user provides "I have been learning Java for 6 weeks now."

Result: 
=======================
WoTech and Java is easy
=======================

I have been learning Java for 6 weeks now.

Plan: 
1. Import scanner
2. Ask for title
3. Ask for description
4. Create a method that will wrap the title
5. Print out wrapped title and then print out description
*/

```java
      import java.util.Scanner;

      public class Main {
        public static void main(String[] args) {
          Scanner scanner = new Scanner(System.in);

          System.out.println("Enter a title: ");
          String title = scanner.nextLine();
          System.out.println("Enter a description: ");
          String description = scanner.nextLine();

          wrappedTitle(title);
          System.out.println(description); 

          scanner.close();
        }
        
    public static void wrappedTitle(String title) {
    int titleLength = title.length();
    int padding = titleLength;
      for (int i = 0; i < padding; i++) {
        System.out.print("=");
      }
      System.out.println();
      
      System.out.print(title);

      System.out.println();
      
      for (int i = 0; i < padding; i++) {
        System.out.print("=");
      }
      System.out.println();
      }
      }
```

## Methods explanations

```java
public class Main {
  public static void main(String[] args) {
    int number = 51;
    checkNumber(number);
    
    int number2 = 49;
    checkNumber(number2);
    
    int number3 = 117;
    checkNumber(number3);
    
    int number4 = 50;
    checkNumber(number4);
    }

  // Void is just for action, we don't need to return anything
  // int is returning a number
  // string is returnig a text
  // double is returning a double
  // boolean is returning a true or false
  // ...

public static void checkNumber(int number){
  if(number > 50){
    System.out.println("Number is greater than 50");
  } else if(number < 50){
    System.out.println("Number is less than 50");
  } else{
    System.out.println("Number is equal to 50");  
  }
}
}
```

## Using public static string and return
```java
public class Main {
  public static void main(String[] args) {
    int number = 51;
    String result = checkNumber(number);
    System.out.println(result);

    int number2 = 49;
    String result2 = checkNumber(number2);
    System.out.println(result2);
    
    int number3 = 117;
    String result3 = checkNumber(number3);
    System.out.println(result3);
    
    int number4 = 50;
    String result4 = checkNumber(number4);
    System.out.println(result4);
  }

  // Void is just for action, we don't need to return anything
  // int is returning a number
  // string is returnig a text
  // double is returning a double
  // boolean is returning a true or false
  // ...
  
public static String checkNumber(int number){
  if(number > 50){
    return "Number is greater than 50";
  } else if(number < 50){
    return "Number is less than 50";
  } else{
    return "Number is equal to 50";  
  }
}
}

// if we want to return a text, then instead of void, we have to use String
```

```java
  import java.util.Scanner;

  /*
    Ask user for a title - inputText()
    Ask user for a description - inputText()
  */

  public class Main {
    public static void main(String[] args) {

      //Creating scanner
      Scanner scanner = new Scanner(System.in);

      //Calling method for getting title
      System.out.print("Enter a title: ");
      String title = getText();

      System.out.print("Enter a description: ");
      String description = getText();

      //Calling method to get printout with lines
      getPrintout(title, description);

      //Closing scanner
      scanner.close();
    }

    // Method to ask user for description
    public static String getText() {
      Scanner scanner = new Scanner(System.in);

      //Read user input
      String text = scanner.nextLine();

      //Return user input
      return text;
    }

      // Method to display the result with the title wrapped in = characters + description
    /* PrintInformation()
      Figure out the size of title
      Print out a border of the size of the title -> printBorder()
      Print out the title
      Print out a border of the size of the title -> printBorder()
      Print out the description
    */

    public static void getPrintout(String title, String description) {

      // Calc length
      int length = title.length();
      // Create top border
      printBorder(length);
      // Display the title
      System.out.print(title);

      System.out.println("");
      // Create bottom border
      printBorder(length);

      // Display the description
      System.out.println("");
      System.out.println(description);

    }
    public static void printBorder(int length){
      for (int i = 0; i < (length); i++) {
        System.out.print("=");
      }
      System.out.println("");
    }
  }
```

## Another example
```java
public class Main {
  public static void main(String[] args) {
    int money = 25;

    String result = buyJeans(money);
    System.out.println(result);
  }

  public static String buyJeans(int money){
    int price = 30;
    if(money > price)
    {
      return "Person can afford Jeans";
    }else{
      return "Person cannot afford Jeans";
    }
  }
}
```

## Antoher example for RESULT
```java
// 7, 12, 18 
// Needs to sum them all together


public class Main {
  public static void main(String[] args) {
    int number1 = 7;
    int number2 = 12;

    int number3 = 18;

    int result = sum(number1, number2); // 7 + 12 = 19

    int finalResult = sum(result, number3); // 19 + 18 = 37

    System.out.println(finalResult);
  }

  public static int sum(int a, int b){
    return a + b;
  }
}
```
```
