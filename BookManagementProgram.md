### Main.java

/*
Develop a simple book management application with ArrayList.
User should be able to add a book to ArrayList.
User should be able to remove a book from ArrayList.
*/

```java
import java.util.Scanner;
import java.util.List;

public class Main {

  public static BookManager bookManager = new BookManager();
  private static Scanner scanner = new Scanner(System.in);
  
  public static void main(String[] args) {
    actionPlan();
  }
  public static void createBook(){
    System.out.println("Which book would you like to add?");
    String title = scanner.nextLine();
    Book book = new Book(title);
    bookManager.addBook(book);
  }

  public static void removeBook(){
    System.out.println("Which book would you like to remove?");
    String bookTitle = scanner.nextLine();
    bookManager.removeBook(bookTitle); 
     }
  
  public static void markBookAsRead(){
    System.out.println("Which book have you finished reading?");
    String bookTitle = scanner.nextLine();
    bookManager.markBookAsRead(bookTitle);
    }
  
  public static void showBookList (){
    List<Book> books = bookManager.getBooks();
    for (Book book : books){
      System.out.println(book.title);
      System.out.println(book.isRead);
    }
  }
  public static void actionPlan(){
    while(true){
      System.out.println("Choose what you would like to do:");
      System.out.println("  Press 1 to Add a book");
      System.out.println("  Press 2 to Remove a book");
      System.out.println("  Press 3 to See the booklist");
      System.out.println("  Press 4 to Mark a book as read");
      System.out.println("  Press x to Exit");

      String userInput = scanner.nextLine();
      if(userInput.equals("x")){
        System.out.println("Done for today. Bye!");
        break;
      }
      if(userInput.equals("1")){
        createBook();
        System.out.println("Your book has been added.");
      }else if(userInput.equals("2")){
        removeBook(); // how does this work better than removeBook(bookTitle)?
        System.out.println("Your book has been removed.");
      }else if(userInput.equals("3")){
        System.out.println("Your booklist is as follows: ");
        showBookList();
      }else if(userInput.equals("4")){
        System.out.println("Enter the book you've finished reading.");
        String bookTitle = scanner.nextLine();
        System.out.println("Glad to see you have finished " + bookTitle + ".");
        bookManager.markBookAsRead(bookTitle);
      }else{
        System.out.println("Invalid input. Please try again.");
      }
    } 
    scanner.close();
  }
}
```

### BookManager.java
```java
import java.util.ArrayList;
import java.util.stream.Collectors;
import java.util.List;

public class BookManager{
  private ArrayList<Book> books = new ArrayList<Book>();

  public void addBook(Book book){
    books.add(book);
  }

  public void removeBook(String bookTitle){
    books.removeIf(book -> book.getTitle().equals(bookTitle));
  }
 
  public ArrayList<Book> getBooks(){
    return new ArrayList<>(books);
  }
  
  public void markBookAsRead(String bookTitle){
    books.stream()
      .filter(book -> book.getTitle().equals(bookTitle))
      .findFirst()
      .ifPresent(book -> book.setRead(true));
  }
}
```

### Book.java
```java
public class Book {
  public String title;
  public boolean isRead;
  // public boolean isListed;

  public Book(String title) {
    this.title = title;
  }

public String getTitle() {
	return title;
}
  
public boolean isRead() {
	return isRead;
}
  
public void setRead(boolean isRead) {
	this.isRead = isRead;
}
}
