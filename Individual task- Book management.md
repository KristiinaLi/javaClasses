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

## Work in progress
### Main.java
/*
Develop a simple book management application with ArrayList.
User should be able to add a book to ArrayList.
User should be able to remove a book from ArrayList.

Easy: Work with String in ArrayList. All the actions should be available for user.

Medium: Work with String User should be able to repeat all the actions infinitely.

Hard: Create a Book class and work with Book object to the ArrayList.
*/

```java
import java.util.Scanner;

public class Main {

  public static BookManager bookManager = new BookManager();
  
  public static void main(String[] args) {
    actionPlan();
  }
  public static void createBook(){
    Scanner scanner = new Scanner(System.in);
    System.out.println("Which book would you like to add?");
    var title = scanner.nextLine();
    var book = new Book(title);
    bookManager.addBook(book);
  }
  public static void deleteBook(Book book, boolean isListed){
    Scanner scanner = new Scanner(System.in);
    System.out.println("Which book would you like to remove?");
    book = scanner.nextLine();
    // var books = bookManager.getBooks();
    // for (book : books){
    bookManager.removeBook(book);
  }
  /*
  public static void bookRead(){
    Scanner scanner = new Scanner(System.in);
    System.out.println("Which book would you like to mark as read?");
    Book book.title = scanner.nextLine();
    if(book.title books){
      bookManager.markBookAsRead(book.title);
    }else{
      continue;
    }
    */
  
  public static void showBookList (){
    var books = bookManager.getBooks();
    for (var book : books){
      System.out.println(book.title);
      System.out.println(book.isRead);
    }
  }
  public static void actionPlan(){
    while(true){
      Scanner scanner = new Scanner(System.in);
      System.out.println("Choose what you would like to do:");
      System.out.println("  Press 1 to Add a book");
      System.out.println("  Press 2 to Remove a book");
      System.out.println("  Press 3 to See the booklist");
      System.out.println("  Press 4 to Mark a book as read");
      System.out.println("  Press x to Exit");

      var userInput = scanner.nextLine();
      if(userInput.equals("x")){
        System.out.println("Done for today. Bye!");
        break;
      }
      if(userInput.equals("1")){
        createBook();
        System.out.println("Your book + " + userInput + " has been added.");
      }else if(userInput.equals("2")){
        deleteBook();
        System.out.println("Your book + " + userInput + " has been removed.");
      }else if(userInput.equals("3")){
        System.out.println("Your booklist is as follows: ");
        showBookList();
      }else if(userInput.equals("4")){
        System.out.println("Enter the book you've finished reading.");
        var bookTitle = scanner.nextLine();
        System.out.println("Glad to see you have finished " + bookTitle + ".");
        bookManager.markBookAsRead(bookTitle);
      }else{
        System.out.println("Invalid input. Please try again.");
      }
    }}}
```

### BookManager.java
```java
import java.util.ArrayList;
import java.util.stream.Collectors;

public class BookManager{
  private ArrayList<Book> books = new ArrayList<Book>();

  public void addBook(Book book){
    books.add(book);
  }
  public void removeBook(String book, boolean isListed){
    if (isListed = true){
    books.remove(book);
  }
}
  public ArrayList<Book> getBooks(){
    return books;
  }
  
  public void markBookAsRead(String bookTitle){
    books.stream()
      .filter(x -> x.title.equals(bookTitle))
      .findFirst()
      .ifPresent(x -> x.isRead = true);
//    Book isRead = true;
  }
}
```

## Book.java
```java
public class Book {
  public String title;
  public boolean isRead;
  public boolean isListed;

  public Book(String title) {
    this.title = title;
  }
}
```

# Possibly working version - remove doesn't work
## Main.java
```java
/*
Develop a simple book management application with ArrayList.
User should be able to add a book to ArrayList.
User should be able to remove a book from ArrayList.

Easy: Work with String in ArrayList. All the actions should be available for user.

Medium: Work with String User should be able to repeat all the actions infinitely.

Hard: Create a Book class and work with Book object to the ArrayList.
*/

import java.util.Scanner;

public class Main {

  public static BookManager bookManager = new BookManager();
  
  public static void main(String[] args) {
    actionPlan();
  }
  public static void createBook(){
    Scanner scanner = new Scanner(System.in);
    System.out.println("Which book would you like to add?");
    var title = scanner.nextLine();
    var book = new Book(title);
    bookManager.addBook(book);
  }

  public static void removeBook(){
    Scanner scanner = new Scanner(System.in);
    System.out.println("Which book would you like to remove?");
    var title = scanner.nextLine();
    bookManager.removeBook(title);
  }
  
  public static void showBookList (){
    var books = bookManager.getBooks();
    for (var book : books){
      System.out.println(book.title);
      System.out.println(book.isRead);
    }
  }
  public static void actionPlan(){
    while(true){
      Scanner scanner = new Scanner(System.in);
      System.out.println("Choose what you would like to do:");
      System.out.println("  Press 1 to Add a book");
      System.out.println("  Press 2 to Remove a book");
      System.out.println("  Press 3 to See the booklist");
      System.out.println("  Press 4 to Mark a book as read");
      System.out.println("  Press x to Exit");

      var userInput = scanner.nextLine();
      if(userInput.equals("x")){
        System.out.println("Done for today. Bye!");
        break;
      }
      if(userInput.equals("1")){
        createBook();
        System.out.println("Your book has been added.");
      }else if(userInput.equals("2")){
        removeBook();
        System.out.println("Your book has been removed.");
      }else if(userInput.equals("3")){
        System.out.println("Your booklist is as follows: ");
        showBookList();
      }else if(userInput.equals("4")){
        System.out.println("Enter the book you've finished reading.");
        var bookTitle = scanner.nextLine();
        System.out.println("Glad to see you have finished " + bookTitle + ".");
        bookManager.markBookAsRead(bookTitle);
      }else{
        System.out.println("Invalid input. Please try again.");
      }
    }}}
```

## BookManager.java
```java
import java.util.ArrayList;
import java.util.stream.Collectors;

public class BookManager{
  private ArrayList<Book> books = new ArrayList<Book>();

  public void addBook(Book book){
    books.add(book);
  }

// create a method to remove a book from books by name
  public void removeBook(String title){
    books.remove(title);
  }

  public ArrayList<Book> getBooks(){
    return books;
  }
  
  public void markBookAsRead(String bookTitle){
    books.stream()
      .filter(x -> x.title.equals(bookTitle))
      .findFirst()
      .ifPresent(x -> x.isRead = true);
  }
}
```

Book.java
```java
public class Book {
  public String title;
  public boolean isRead;
  public boolean isListed;

  public Book(String title) {
    this.title = title;
  }
}
```

