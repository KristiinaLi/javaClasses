## Classes and constructors

```java
import java.util.ArrayList;
import java.util.stream.Collectors;
import java.util.Scanner;

/*
A class is a package or a description. When we launch code we create a class and run the main function.
*/
public class Main {
  public static void main(String[] args) {
    Person person = new Person(); // new  creates an instance of the class; reference type 
    person.name = "Oskars"; // putting a value into name property
    person.surname = "Klaumanis";
    
    Person person2 = new Person();
    person2.name = "Elchin"; 
    person2.surname = "Datorium";


    System.out.println(person.name); // printing out person's name
    System.out.println(person.surname);
    System.out.println(person2.name);
    System.out.println(person2.surname);

    // Create an ArrayList out of the Person class

    ArrayList<Person> persons = new ArrayList<Person>();
  }
}

/*
Use Scanner and System.out.println only in Main class.
*/
```

```java
// creating a new class // if private, then we can't access it outside of the class
// object oriented programming; always going to work with objects (person, book, insurance, profile, etc). 
// We pass complex data to a user or to another program.
// Creating complext objects that have a lot of different values to it

// Two classes: either 
// DTO (data transfer object) - description of an object 
// POJO (plain old java object) - service works with the DTO

// We can create methods in new classes
// THis person can have multiple instances

// A class should have only one object 

// We could use this new class to create a treasure map, and hide a prize somewhere in the map.

// We could create a get age method in this class to calculate the age from this year - his/her birth year.

// Class is a blueprint for object, method is a blueprint for action

// There can be a class without a method, but not a method without a class

// Constructor launches itself, when an object is created.
// Set up data or set up an object for something.

public class Person {
  
    public String name; //contains a value called "name"
    public String surname;
    public Integer birthyear;

  // this is a constructor, it is a method that is called when an object is created --> new Person(name, surname);
  // constructor is a function, that is called when an object is created
  // no data type, it is retunring a person
  // You can provide values to constructor

  // "this" keyword is describing current class

 
  public Person(String inputName, String inputSurname){
    name = inputName;
    surname = inputSurname;
  }

  // new Person();
  public Person(){
  
  /*
  public static int getAge (int birthyear, int currentYear){
    System.out.println(currentYear - birthyear = "");
  */
  }
}

```

```java
public class Main {
  public static void main(String[] args) {
    var book = new Book();
    book.title = "The Hobbit";
    book.author = "J.R.R. Tolkien";
    book.pageCount = 310;

    System.out.println(book.title);
    System.out.println(book.author);
    System.out.println(book.pageCount);
}
}

// A book, that has it's author, and book title to it. 
// We create a book, and then we print out the values of the book in a fancy way. 

// Title
// ----------------------------------
```

```java
public class Book{
  public String title;
  public String author;
  public int pageCount;
}
```

```java
public class Main {
  public static void main(String[] args) {
    var book = new Book("The Hobbit", "J.R.R. Tolkien", 310);
    
    System.out.println(book.title);
    System.out.println(book.author);
    System.out.println(book.pageCount);

    var book2 = new Book();
    System.out.println(book2.title);
    System.out.println(book2.author);
    System.out.println(book2.pageCount);
}
}

// A book, that has it's author, and book title to it. 
// We create a book, and then we print out the values of the book in a fancy way. 

// Title
// ----------------------------------
// Author
```

```java
public class Book{
  public String title;
  public String author;
  public int pageCount;

  // "this" means that we are going to use the variables in this class
  
  public Book (String title, String author, int pageCount){
    this.title = title;
    this.author = author;
    this.pageCount = pageCount;
  }

  public Book(){
    this.title = "Unknown";
    this.author = "Unknown";
  }
  }
```

```java
public class Main {
  public static void main(String[] args) {
    var book = new Book("The Hobbit", "J.R.R. Tolkien", 310);
// Reference of the book object is stored in the variable book
    
    System.out.println(book.title);
    System.out.println(book.author);
    System.out.println(book.pageCount);

    var book2 = new Book(); // creates a new object with different values
    System.out.println(book2.title);
    System.out.println(book2.author);
    System.out.println(book2.pageCount);

    new Book();
    new Book();
    new Book();
    new Book();

    System.out.println(Book.totalBookCount);
}
}

// A book, that has it's author, and book title to it. 
// We create a book, and then we print out the values of the book in a fancy way. 

// Title
// ----------------------------------
// Author
```

```java
public class Book{
  public static int totalBookCount = 0; // always has the same value
  public String title;
  public String author;
  public int pageCount;

  // "this" means that we are going to use the variables in this class
  // A class that has no attributes, provides a service
  
  public Book (String title, String author, int pageCount){
    this.title = title;
    this.author = author;
    this.pageCount = pageCount;
    totalBookCount++;
  }

  public Book(){
    this.title = "Unknown";
    this.author = "Unknown";
    totalBookCount++;
  }
  }
```
## Create a class for an object that you can find on your table or for something you own - 
For example: Vehicle
Brand
Year
Color
OwnersName

Initialize 3 different objects out of this class, and print it out.

Try to use as many data types as you can (int, String, boolean and so on)

```java
public class Main {
  public static void main(String[] args) {
    var vehicle = new Vehicle("bicycle", "Scott", 2017, "red", true, 'S', 577.99f);
    System.out.println("The first vehicle is a " + vehicle.color + " " + vehicle.brand  + " " + vehicle.type + " made in the year " + vehicle.year + "." + " It is a two wheeler " + "(" + vehicle.twoWheeler + ")" + " with an initial " + "*" + vehicle.initial + "*" + " and costs " + vehicle.price + "€.");
    System.out.println();
    /*
    System.out.println(vehicle.type);
    System.out.println(vehicle.brand);
    System.out.println(vehicle.year);
    System.out.println(vehicle.color);
    System.out.println(vehicle.twoWheeler);
    System.out.println(vehicle.initial);
    System.out.println(vehicle.price);
    */

    var vehicle2 = new Vehicle("car", "Toyota", 2020, "black", false, 'T', 20000.55f);
    System.out.println("The second vehicle is a " + vehicle2.color + " " + vehicle2.brand  + " " + vehicle2.type + " made in the year " + vehicle2.year + "." + " It is a two wheeler " + "(" + vehicle2.twoWheeler + ")" + " with an initial " + "*" + vehicle2.initial + "*" + " and costs " + vehicle2.price + "€.");
    System.out.println();
    /*
    System.out.println(vehicle2.type);
    System.out.println(vehicle2.brand);
    System.out.println(vehicle2.year);
    System.out.println(vehicle2.color);
    System.out.println(vehicle2.twoWheeler);
    System.out.println(vehicle2.initial);
    System.out.println(vehicle2.price);
    */

    var vehicle3 = new Vehicle("motorcycle", "Harley Davidson", 2021, "blue", true, 'H', 19012.23f);
    System.out.println("The third vehicle is a " + vehicle3.color + " " + vehicle3.brand  + " " + vehicle3.type + " made in the year " + vehicle3.year + "." + " It is a two wheeler " + "(" + vehicle3.twoWheeler + ")" + " with an initial " + "*" + vehicle3.initial + "*" + " and costs " + vehicle3.price + "€.");
    System.out.println();
    /*
    System.out.println(vehicle3.type);
    System.out.println(vehicle3.brand);
    System.out.println(vehicle3.year);
    System.out.println(vehicle3.color);
    System.out.println(vehicle3.twoWheeler);
    System.out.println(vehicle3.initial);
    System.out.println(vehicle3.price);
    */

    var vehicle4 = new Vehicle("boat", "Yacht", 2019, "gray", false, 'Y', 32300.11f);
    System.out.println("The fourth vehicle is a " + vehicle4.color + " " + vehicle4.brand  + " " + vehicle4.type + " made in the year " + vehicle4.year + "." + " It is a two wheeler " + "(" + vehicle4.twoWheeler + ")" + " with an initial " + "*" + vehicle4.initial + "*" + " and costs " + vehicle4.price + "€.");
    System.out.println();
    /*
    System.out.println(vehicle4.type);
    System.out.println(vehicle4.brand);
    System.out.println(vehicle4.year);
    System.out.println(vehicle4.color);
    System.out.println(vehicle4.twoWheeler);
    System.out.println(vehicle4.initial);
    System.out.println(vehicle4.price);
    */
    
    var vehicle5 = new Vehicle("airplane", "Boeing 747", 2021, "white", false, 'B', 1632300.14f);
    System.out.println("The fifth vehicle is a " + vehicle5.color + " " + vehicle5.brand  + " " + vehicle5.type + " made in the year " + vehicle5.year + "." + " It is a two wheeler " + "(" + vehicle5.twoWheeler + ")" + " with an initial " + "*" + vehicle5.initial + "*" + " and costs " + vehicle5.price + "€.");
    System.out.println();
    /*
    System.out.println(vehicle5.type);
    System.out.println(vehicle5.brand);
    System.out.println(vehicle5.year);
    System.out.println(vehicle5.color);
    System.out.println(vehicle5.twoWheeler);
    System.out.println(vehicle5.initial);
    System.out.println(vehicle5.price);
  */
    
    System.out.println("In total there are " + Vehicle.vehicleCount + " vehicles on our table.");
    }
  }
```
## The Vehicle class

```java
public class Vehicle{
    public static int vehicleCount = 0;
    public String type;
    public String brand;
    public int year;
    public String color;
    public boolean twoWheeler;
    public char initial;
    public float price;
    
 
  public Vehicle(String type, String brand, int year, String color, boolean twoWheeler, char initial, float price){
    this.type = type;
    this.brand = brand;
    this.year = year;
    this.color = color;
    this.twoWheeler = twoWheeler;
    this.initial = initial;
    this.price = price;
    vehicleCount++;
  } 
}
```
