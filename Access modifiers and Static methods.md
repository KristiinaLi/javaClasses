## Access modifiers and Static methods

// Access modifiers and Static Methods

# Main class
```java
public class Main {
  public static void main(String[] args) {
    Student.studentCount = 10; 
    // static means that it is global variable which belongs to the student class. We don't need to create an object to access it. Don't use static outside of Main method. 
    
    Student student = new Student();
    student.name = "John";
    Student student2 = new Student();
    System.out.println(student2.name);
    System.out.println(student.studentCount); 
    // variable student created from the class or template
    System.out.println(student2.studentCount);
    System.out.println(Student.studentCount); 
    // Student class
    Main.main(args);
  }
}
```

# Student class
```java
public class Student {
  public static int studentCount; 
  
  /*it is always going to be 0 for int, float, double; and it's always going to be false for boolean.
   this is a global variable, that anyone can use, everywhere.
  */
  
  public String name; 
  public int age;
  }
```

# Main class
```java
public class Main {
  public static void main(String[] args) {
    Square square1 = new Square(3);
    var square1Perimeter = square1.getPerimeter();
    var square1FieldSize = square1.getField();
    System.out.println(square1Perimeter);
    System.out.println(square1FieldSize);

    var square2 = new Square(4);
    System.out.println(square2.getPerimeter());

    var square3 = new Square(100);
    System.out.println(square3.getPerimeter());

    var square4 = new Square(1);
    System.out.println(square4.getPerimeter());
  }
}
```
# Square class
```java
public class Square {
  public int sideLength; // sideLength = 7
  // new Square(7); 
  public Square(int sideLength) {
    this.sideLength = sideLength;
  }
  public int getPerimeter(){
    return sideLength * 4;
  }
  // var square1 = new Square (10);
  // var fieldSize = square1.getField();
  public int getField(){
    return sideLength * sideLength;
  }
}
```
