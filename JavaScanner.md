# Scanner

## 1

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner myObj = new Scanner(System.in);

        System.out.println("Enter name");
        String name = myObj.nextLine();

        System.out.println("Enter age");
        int age = myObj.nextInt();
        myObj.nextLine(); // Consume newline left by nextInt()

        if (age < 18) {
            System.out.println("You are not old enough to work");
            System.out.println("Are you studying?");
            String studyingInput = myObj.nextLine();
            boolean studying = false;
            if (studyingInput.equalsIgnoreCase("yes")) {
                studying = true;
            } else if (studyingInput.equalsIgnoreCase("no")) {
                studying = false;
            } else {
                System.out.println("Invalid input. Please enter 'yes' or 'no'.");
                return; // Exit the program if input is invalid
            }

            if (studying) {
                System.out.println("Hope you become a programmer!");
            } else {
                System.out.println("You should study");
            }
        } else {
            System.out.println("Enter income");
            double salary = myObj.nextDouble();
            System.out.println("Hello, " + name + ". It's great that you are " + age + " years old and earn " + salary + " per year.");
        }

        myObj.close(); // Remember to close the scanner

## 2

import java.util.Scanner;

public class Main {
  public static void main(String[] args) {

    Scanner scanner = new Scanner(System.in); //Opening channel

    int number; //number = 7
    number = scanner.nextInt(); // Waits for us to provide an integer
    System.out.println("This is the provided number:" + number);

    System.out.println("Hello!");
    int age;
    System.out.println("What is your age?");
    age = scanner.nextInt();
    System.out.println("The user's age is: " + age);
    
    scanner.close(); // Closing the chnanel

    //scanner.nextLine(); // Waits for us to provide a string until pressed enter 
  }
}
    }
}

## 3

import java.util.Scanner;

public class Main {
  public static void main(String[] args) {

    Scanner scanner = new Scanner(System.in); //Opening channel

    System.out.println("Write a number:");
    int a = scanner.nextInt(); //Reads the number
    System.out.println("Write another number:");
    int b = scanner.nextInt(); //Reads the number;

    System.out.println("A sum of A and B is " + (a + b));
    
    scanner.close(); // Closing the chnanel

    //scanner.nextLine(); // Waits for us to provide a string until pressed enter 
  }
}
