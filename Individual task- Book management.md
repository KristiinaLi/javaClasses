## Book management application
Develop a simple book management application with ArrayList.
User should be able to add a book to ArrayList.
User should be able to remove a book from ArrayList.
User should be able to delete a book from ArrayList.

Easy: Work with String in ArrayList. All the actions should be available for user.

Medium: Work with String User should be able to repeat all the actions infinitely.

Hard: Create a Book class and work with Book object to the ArrayList.

# First part try-out
```java
import java.util.ArrayList;
import java.util.stream.Collectors;
import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
    ArrayList<String> books = new ArrayList<>();
    Scanner scanner = new Scanner(System.in);
    for (int i = 0; i < 10; i++){
      System.out.println("What is the title of your book?");
    books.add(scanner.nextLine());
    System.out.println(books);
  }
  }
}
```
