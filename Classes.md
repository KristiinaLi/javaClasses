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
  // no data type, it is retunring a person
  // You can provide values to constructor

  // this keyword is describing current class
  
  public Person(String inputName, String inputSurname){
    System.out.println("TEST 123");
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
