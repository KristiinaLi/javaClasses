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

## ArrayLists and Streams

```java
import java.util.ArrayList;
import java.util.stream.Collectors;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        var shopsItems = new ArrayList<String>();
        shopsItems.add("Glass Table");
        shopsItems.add("Wooden table");
        shopsItems.add("Round table");
        shopsItems.add("Chair");
        shopsItems.add("Doors");
        shopsItems.add("Trapdoor");
        shopsItems.add("Couch");
        shopsItems.add("Bed");


        var filteredShopsItems = new ArrayList<String>();
        for (var item: shopsItems){
          if(item.contains("table")){
            filteredShopsItems.add(item);
          }
        }
      System.out.println(filteredShopsItems);
    }
}
```

```java
import java.util.ArrayList;
import java.util.stream.Collectors;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        var shopsItems = new ArrayList<String>();
        shopsItems.add("Glass Table");
        shopsItems.add("Wooden Table");
        shopsItems.add("Round Table");
        shopsItems.add("Chair");
        shopsItems.add("Doors");
        shopsItems.add("Trapdoor");
        shopsItems.add("Couch");
        shopsItems.add("Bed");

        // shopsItems.removeIf(x -> x.contains("table"));

      //How can I filter the elements, how can I collect elements?
        var filteredShopsItems = shopsItems
          .stream()
          .filter(item -> item.toLowerCase().contains("table"))
          .collect(Collectors.toList());

      //Exception: all of these are functions, and we can write them on different lines, without ";" at the end. 

        System.out.println(filteredShopsItems);
    }
}
```

```java
import java.util.ArrayList;
import java.util.stream.Collectors;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        var shopsItems = new ArrayList<String>();
        shopsItems.add("Glass Table");
        shopsItems.add("Wooden Table");
        shopsItems.add("Round Table");
        shopsItems.add("Chair");
        shopsItems.add("Doors");
        shopsItems.add("Trapdoor");
        shopsItems.add("Couch");
        shopsItems.add("Bed");

      //Search bar
      /*
      Scanner sc = new Scanner(System.in);
      String searchWord = sc.nextLine();
      */
      
        // shopsItems.removeIf(x -> x.contains("table"));

      //How can I filter the elements, how can I collect elements?
        var filteredShopsItems = shopsItems
          .stream()
          .filter(item -> item.toLowerCase().contains("table"))
          .collect(Collectors.toList());

      //Exception: all of these are functions, and we can write them on different lines, without ";" at the end. 

        System.out.println(filteredShopsItems);
    }
}
```

```java
import java.util.ArrayList;
import java.util.stream.Collectors;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        var shopsItems = new ArrayList<String>();
        shopsItems.add("Glass Table");
        shopsItems.add("Wooden Table");
        shopsItems.add("Round Table");
        shopsItems.add("Chair");
        shopsItems.add("Doors");
        shopsItems.add("Trapdoor");
        shopsItems.add("Couch");
        shopsItems.add("Bed");

      //Search bar
      /*
      Scanner sc = new Scanner(System.in);
      String searchWord = sc.nextLine();
      */
      
        // shopsItems.removeIf(x -> x.contains("table"));

      //How can I filter the elements, how can I collect elements?
        var filteredShopsItems = shopsItems
          .stream()
          //We can do actions here
          .skip(3)
          .limit(2)
          .collect(Collectors.toList());

      //Exception: all of these are functions, and we can write them on different lines, without ";" at the end. 

        System.out.println(filteredShopsItems);
    }
}
```

```java
import java.util.ArrayList;
import java.util.stream.Collectors;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        var shopsItems = new ArrayList<String>();
        shopsItems.add("Glass Table");
        shopsItems.add("Wooden Table");
        shopsItems.add("Round Table");
        shopsItems.add("Chair");
        shopsItems.add("Doors");
        shopsItems.add("Trapdoor");
        shopsItems.add("Couch");
        shopsItems.add("Bed");

        // shopsItems.removeIf(x -> x.contains("table"));

        shopsItems
          .stream()
          .skip(3)
          .limit(2)
          .forEach(x -> System.out.println("TEST " + x));
         
    }
}
```

```java
import java.util.ArrayList;
import java.util.stream.Collectors;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        var shopsItems = new ArrayList<String>();
        shopsItems.add("Glass Table");
        shopsItems.add("Wooden Table");
        shopsItems.add("Round Table");
        shopsItems.add("Chair");
        shopsItems.add("Doors");
        shopsItems.add("Trapdoor");
        shopsItems.add("Couch");
        shopsItems.add("Bed");

      //Search bar
      /*
      Scanner sc = new Scanner(System.in);
      String searchWord = sc.nextLine();
      */
      
        // shopsItems.removeIf(x -> x.contains("table"));

      /*
      for (var item: shopsItems){
        System.out.println(item); 
      }

       is the same as 
.filter(x -> x.contains("table"))
.forEach(x -> System.out.println("TEST " + x));
        */

        shopsItems
          .stream()
          .filter(x -> x.contains("table"))
          .forEach(x -> System.out.println("TEST " + x));
    }
}
```

## Stream functions 
Terminal Operations: stream() can be followed by various terminal operations like forEach(), reduce(), count(), findFirst(), anyMatch(), allMatch(), noneMatch(), etc.

## Group work

/*
Easy: Create an integer ArrayList, skip the first 5 numbers. And then with the rest of them, print them out.
*/

## Easy
```java
import java.util.ArrayList;
import java.util.stream.Collectors;
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
    var numbers = new ArrayList<Integer>();
    numbers.add(9);
    numbers.add(14);
    numbers.add(19);
    numbers.add(31);
    numbers.add(26);
    numbers.add(28);
    numbers.add(49);
    numbers.add(53);
    numbers.add(67);
    numbers.add(87);

    numbers
      .stream()
      .skip(5)
      .forEach(x -> Print(x));
    } 

  public static void Print(Integer number) {
     System.out.println();
     System.out.println(number);
     }
}
```

## Something between easy and medium

```java
import java.util.ArrayList;
import java.util.stream.Collectors;
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
    var numbers = new ArrayList<Integer>();
    numbers.add(9);
    numbers.add(14);
    numbers.add(19);
    numbers.add(31);
    numbers.add(26);
    numbers.add(28);
    numbers.add(49);
    numbers.add(53);
    numbers.add(67);
    numbers.add(87);

    for (int number: numbers){
      if (number % 2 == 0){
        Print(number);
      }
    }
    
    numbers
      .stream()
      .skip(5)
      .collect(Collectors.toList());
    } 

  public static void Print(Integer number) {
     System.out.println();
     System.out.println(number);
     return;
     }
}

```

/*
Medium: Create an integer ArrayList, make sure they divide by 2, skip the first 5, limit to three and print them out from another function.
*/

## Medium
```java
import java.util.ArrayList;
import java.util.stream.Collectors;
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
    var numbers = new ArrayList<Integer>();
    numbers.add(9);
    numbers.add(16);
    numbers.add(19);
    numbers.add(26);
    numbers.add(28);
    numbers.add(31);
    numbers.add(36);
    numbers.add(44);
    numbers.add(50);
    numbers.add(53);
    numbers.add(74);
    numbers.add(68);
    numbers.add(88);
   
    numbers
      .stream()
      .filter(number -> number % 2 == 0)
      .skip(5)
      .limit(3)
      .forEach(x -> Print(x));
    } 

  public static void Print(Integer number) {
     System.out.println();
     System.out.println(number);
     return;
     }
}

```
