## Book management application
Develop a simple book management application with ArrayList.
User should be able to add a book to ArrayList.
User should be able to remove a book from ArrayList.
User should be able to delete a book from ArrayList.

Easy: Work with String in ArrayList. All the actions should be available for user.

Medium: Work with String User should be able to repeat all the actions infinitely.

Hard: Create a Book class and work with Book object to the ArrayList.

# Difference between remove and delete
Question: 
What's the difference between using delete and remove?
Isn’t using del and .remove() the same thing? I tried using del in the lesson that waas teaching me about remove but it didn’t work so I used .remove() instead. Why would it matter that I used ‘del’ instead of .remove()?

Answer:
del and .remove() achieve the same effect, but get at the data differently, so quite often, you would prefer one over the other. If you have the index of the item to be eliminated, del is probably best. But if you have the value that you want to eliminate, .remove() is likely to be best.

Each of them get rid of one item at a time; in the case of .remove(), it is the first item with the specified value.


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
