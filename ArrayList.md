## ArrayList
/* How to clear the screen for example at the end of the TicTacToe game to restart the game */ 
/*
System.out.print("\033[H\033[2J");
System.out.flush();
*/

```java
import java.util.ArrayList;
import java.util.stream.Collectors;
import java.util.Scanner;

    public class Main {
        //shopsItems here
        public static void main(String[] args) {
            var shopsItems = new ArrayList<String>();
            //Initializes an ArrayList, creates a new object and gives a reference
            var scanner = new Scanner(System.in);
            while(true){
                var item = scanner.nextLine();
                if(item.equals("exit")){
                    break;
                }
                addItem(shopsItems, item);
            }
            printArrayList(shopsItems);
        }

        public static void printArrayList(ArrayList<String> items){
            for (String item : items){
                System.out.println(item);
            }
        }

        public static void addItem(ArrayList<String> items, String item){
            items.add(item);
            System.out.println(item + " has been added to the store.");
        }
    }
```

//Initialize ArrayList
// Create an element in the arrayList
// Remove an element
// Get the elements
/* Initializes an ArrayList, creates a new object and gives a reference. We are going to put Strings in it. The braces at the end mean, that we are launching a code that..
*/
    /* ArrayType in the initialisation E or T let's us add anything in the ArrayList
        */
/*Instead of ArrayList<String>, we can just write var*/

    
// Initiate arrayList
// Create an element in the arrayList
// Remove an element
// Get the elements

/*
public String toString()
Returns a string representation of this collection. The string representation consists of a list of the collection's elements in the order they are returned by its iterator, enclosed in square brackets ("[]"). Adjacent elements are separated by the characters ", " (comma and space). Elements are converted to strings as by String.valueOf(Object).
Overrides:
toString in class Object
Returns:
a string representation of this collection
*/

```java
import java.util.ArrayList;
import java.util.stream.Collectors;
import java.util.Scanner;

public class Main {
    //shopsItems here
    public static void main(String[] args) {
        var shopsItems = new ArrayList<String>();
        //Initializes an ArrayList, creates a new object and gives a reference

        // These 2 lines in a function
        shopsItems.add("Table");
        System.out.println("Table has been added to the store");
        //
        
        shopsItems.add("Cupboard");
        System.out.println("Cupboard has been added to the store");


        printArrayList(shopsItems);
    }

    public static void printArrayList(ArrayList<String> items){
        for (String item : items){
            System.out.println(item);
        }
    }
}

//Initialize ArrayList
// Create an element in the arrayList
// Remove an element
// Get the elements
```

```java
import java.util.ArrayList;
import java.util.stream.Collectors;
import java.util.Scanner;

public class Main {
    //shopsItems here
    public static void main(String[] args) {
        var shopsItems = new ArrayList<String>();
        //Initializes an ArrayList, creates a new object and gives a reference
        var scanner = new Scanner(System.in);
        // These 2 lines in a function
        var item = scanner.nextLine(); //Asks the user for input
        shopsItems.add(item); // adds the item to the shopsItems arrayList
        System.out.println(item + " has been added to the store"); // Provide information to the user
        //

        shopsItems.add("Cupboard");
        System.out.println("Cupboard has been added to the store");


        printArrayList(shopsItems);
    }

    public static void printArrayList(ArrayList<String> items){
        for (String item : items){
            System.out.println(item);
        }
    }

    public static void addItem(ArrayList<String> shopsItems, String item){
        shopsItems.add(item); // adds the item to the shopsItems arrayList
        System.out.println(item + " has been added to the store"); // Provide 
    }
}

//Initialize ArrayList
// Create an element in the arrayList
// Remove an element
// Get the elements

```

```java
  import java.util.ArrayList;
  import java.util.stream.Collectors;
  import java.util.Scanner;

  public class Main {
      // shopsItems here
      public static void main(String[] args) {
          var shopsItems = new ArrayList<String>();
          // Initializes an ArrayList, creates a new object and gives a reference
          var scanner = new Scanner(System.in);
          // These 2 lines in a function
          while (true) {
            System.out.println("Enter the item you want to add to the list or type exit to stop: ");

              var item = scanner.nextLine(); // Asks the user for input
              if(item.equals("exit")){
                  break;
              }
              addItem(shopsItems, item);
          }
          printArrayList(shopsItems);

          shopsItems.removeIf(item -> item.equals("Table")); //lambda function
          printArrayList(shopsItems);

          System.out.println("Enter the item you want to remove from the list:");
          var itemToRemove = scanner.nextLine(); // Asks the user for input
          shopsItems.removeIf(item -> item.equals(itemToRemove));

      }

      public static void printArrayList(ArrayList<String> items) {
        System.out.println("Store has these items:");
          for (String item : items) {
              System.out.println(item);
          }
      }

      public static void addItem(ArrayList<String> shopsItems, String item) {
        shopsItems.add(item); // adds the item to the shopsItems arrayList
        System.out.println(item + " has been added to the store"); // Provide information to the user
      }
  }
```


## Groupwork

```java
/*
Easy: Create an arrayList for integers
Add 5 numbers.

Filter the arrayList and print out only numbers that divide by 2 
(number % 2 == 0)
*/

import java.util.ArrayList;
import java.util.stream.Collectors;

public class Main {
  public static void main(String[] args) {
    var numbers = new ArrayList<Integer>();
    numbers.add(53);
    numbers.add(2);
    numbers.add(74);
    numbers.add(9);
    numbers.add(28);

    System.out.println(numbers);

    var filteredArrayList = new ArrayList<Integer>();
    for (Integer number: numbers){
      if (number % 2 == 0){
        filteredArrayList.add(number);
      }
    }
    System.out.println(filteredArrayList);
  }
  }
```


