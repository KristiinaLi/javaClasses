### Java-code-exercises
## Conditionals

```java
double temp = -15.0;

    if (temp <= 5) {
      System.out.println("Wear super warm");
    }
    else if (temp <= 15) {
      System.out.println("Wear warm");
    }
    else if (temp <= 30) {
      System.out.println("Wear normal");
    }
    else {
      System.out.println("You need cooling");
    }
    

public class Main {
  public static void main(String[] args) {
    // System.out.println("Hello world!");
    // winter, spring, summer, autumn
    // warm jacket, t-shirt, swimsuit, rain coat

    String season = "qwerty";
      if (season == "winter") {
        System.out.println("Wear a warm jacket!");
      }
    else if (season.equals("spring")) {
      System.out.println("Wear a T-shirt!");
    }
    else if (season.equals("summer")) {
      System.out.println("Wear a swimming suite!");
    }
    else if (season.equals("autumn")) {
      System.out.println("Wear a rain coat!");
    }
    else {
      System.out.println("I do not recognize this season!");
    }}}}



public class Main {
  public static void main(String[] args) {
    String studentName = "Anna";
    int yearOfSchool = 12;
    double studentAge = 18;
    double grade = 9.7;
    boolean olympicsWinner = true;
    boolean isAgeEligible = studentAge >= 18;
    boolean isGradeEligible = grade >= 8;

    if (isAgeEligible && (isGradeEligible || olympicsWinner)) {
      System.out.println("You are accepted!"); 

    if(isGradeEligible && !olympicsWinner){
      System.out.println("Acceptance criteria: Age and grade!");}

      if(!isGradeEligible && olympicsWinner){
        System.out.println("Acceptance criteria: Age and Olympics!");}

        else{ if(isGradeEligible && olympicsWinner);
          System.out.println("Acceptance criteria: Age, grade and Olympics!");
      }

    } else {
      System.out.println("You are not accepted. Reasons:");

      if (!isAgeEligible && !isGradeEligible && !olympicsWinner) {
        System.out.println("None of the criteria fit.");
      }else{


      if (!isAgeEligible) {
        System.out.println("- You are not eligible due to age.");
      }
      if (!isGradeEligible && !olympicsWinner) {
        System.out.println("- You are not eligible due to insufficient grade and not being an olimpian.");
      }}}}

public class Main {
  public static void main(String[] args) {
    String studentName = "Anna";
    int yearOfSchool = 12;
    double studentAge = 18;
    double grade = 9.7;
    boolean olympicsWinner = true;
    boolean isAgeEligible = studentAge >= 18;
    boolean isGradeEligible = grade >= 8;

    if (isAgeEligible && (isGradeEligible || olympicsWinner)) {
      System.out.println("You are accepted!"); 

    if(isGradeEligible && !olympicsWinner){
      System.out.println("Acceptance criteria: Age and grade!");}

      if(!isGradeEligible && olympicsWinner){
        System.out.println("Acceptance criteria: Age and Olympics!");}

        else{ if(isGradeEligible && olympicsWinner);
          System.out.println("Acceptance criteria: Age, grade and Olympics!");
      }

    } else {
      System.out.println("You are not accepted. Reasons:");

      if (!isAgeEligible && !isGradeEligible && !olympicsWinner) {
        System.out.println("None of the criteria fit.");
      }else{


      if (!isAgeEligible) {
        System.out.println("- You are not eligible due to age.");
      }
      if (!isGradeEligible && !olympicsWinner) {
        System.out.println("- You are not eligible due to insufficient grade and not being an olimpian.");
      }}}}


public class Main {
    public static void main(String[] args) {
        String studentName = "Anna";
        int yearOfSchool = 12;
        double studentAge = 17;
        double grade = 5;
        boolean olympicsWinner = false;

        boolean isAgeEligible = studentAge >= 18;
        boolean isGradeEligible = grade >= 8;

        if (isAgeEligible && (isGradeEligible || olympicsWinner)) {
            System.out.println("You are accepted!");
        } else {
            System.out.println("Try next time!");

            // Provide reasons for rejection
            } 
            if (!isAgeEligible) {
                System.out.println("Age requirement not met.");
            }
            if (!isGradeEligible) {
                System.out.println("Grade requirement not met.");
            }
            if (!olympicsWinner) {
            System.out.println("Not Olympics winner.");
        }}}

public class Main {
  public static void main(String[] args) {
    String studentName = "Anna";
    int yearOfSchool = 12;
    double studentAge = 17;
    double grade = 9.7;
    boolean olympicsWinner = false;
    
    // Our condition
    // Student age must be 18 or older 
    // AND 
    // grade must be more than or equal to 8 OR must win some olympiad
    
    boolean isAgeEligible = studentAge >= 18;
    boolean isGradeEligible = grade >= 8;
    
    
    if (isAgeEligible && (isGradeEligible || olympicsWinner)){
      System.out.println("You are accepted!"); 
    }else{
      System.out.println("Try next time!");
        }}}

public class Main {
  public static void main(String[] args) {
    String studentName = "Anna";
    int yearOfSchool = 12;
    double studentAge = 18.5;
    double grade = 6.8;
    boolean olympicsWinner = true;
    
    // Our condition
    // Student age must be 18 or older 
    // AND 
    // grade must be more than or equal to 8 OR must win some olympiad
    
    boolean isAgeEligible = studentAge >= 18;
    boolean isGradeEligible = grade >= 8;
    
    
    if (isAgeEligible && (isGradeEligible || olympicsWinner)){
      System.out.println("You are accepted!"); 
    }else{
      System.out.println("Try next time!");
        }}}

public class Main {
  public static void main(String[] args) {
    String studentName = "Anna";
    int yearOfSchool = 12;
    double studentAge = 17.6;
    double grade = 9.2;

    // Our condition
    // Student age must be 18 or older 
    // AND 
    // grade must be more than or equal to 8
boolean isAgeEligible = studentAge >= 18;
boolean isGradeEligible = grade >= 8;

    
    if (isAgeEligible && isGradeEligible){
      System.out.println("You are accepted!"); 
    }else{
      System.out.println("Try next time!");
        }}}

public class Main {
    public static void main(String[] args) {
        String studentName = "Anna";
        int yearOfSchool = 12;
        double studentAge = 17;
        double grade = 9;
        boolean olympicsWinner = false;

        boolean isAgeEligible = studentAge >= 18;
        boolean isGradeEligible = grade >= 8;

        if (isAgeEligible && (isGradeEligible || olympicsWinner)) {
            System.out.println("You are accepted!");
        } else {
            System.out.println("Try next time!");

            // Provide reasons for rejection
            } 
            if (!isAgeEligible) {
                System.out.println("Age requirement not met.");
            }
            if (isGradeEligible && !olympicsWinner) {
                System.out.println("Not an Olympics winner.");
            }
            if (!isGradeEligible && olympicsWinner) {
                System.out.println("Grade requirement not met.");
            }}}

public class Main {
  public static void main(String[] args) {
    String studentName = "Anna";
    int yearOfSchool = 12;
    double studentAge = 17.6;
    double grade = 9.2;

    // Our condition
    // Student age must be 18 or older
    // AND
    // grade must be more than or equal to 8

    if(studentAge >= 18 && grade >= 8){
      System.out.println("You are accepted!");
    }else{
      System.out.println("Try next time!");
    }}}

public class Main {
  public static void main(String[] args) {

    var name = "Hanna"; 
    var age = 24.6f;
    var time = 3;
    var newAge = age + time;
    var isUniStudent = false;
    var isWorking = true;
    var numberOfChildren = 0;
    var middleName = 'S';
    var hobbie = "swimming";

    System.out.println(numberOfChildren);
    System.out.println(middleName);
    System.out.println(hobbie);
    System.out.println("Hello, my name is " + name + " " + middleName);
    System.out.println("I am " + age + " years old");
    System.out.println("Am I a UniStudent? " + isUniStudent + "!");
    System.out.println("Am I working? " + isWorking + "!");
    System.out.println("In " + time + " years time I will be " + newAge);
  }}

public class Main {
  public static void main(String[] args) {
    // System.out.println("Hello world!");
    // winter, spring, summer, autumn
    // warm jacket, t-shirt, swimsuit, rain coat

    String season = "qwerty";
      if (season == "winter") {
        System.out.println("Wear a warm jacket!");
      }
    else if (season.equals("spring")) {
      System.out.println("Wear a T-shirt!");
    }
    else if (season.equals("summer")) {
      System.out.println("Wear a swimming suite!");
    }
    else if (season.equals("autumn")) {
      System.out.println("Wear a rain coat!");
    }
    else {
      System.out.println("I do not recognize this season!");
    }}}

public class Main {
  
  public static void main(String[] args) {
  
    // System.out.println("Hello world!");

    String username = "Daiga";
    if (username != "Elchin") { //True
      System.out.println("You can come to the party!");
    } else { 
      System.out.println("Go home!");
    }

    // System.out.println("This code is going to show always");
      }

public class Main {
  
  public static void main(String[] args) {
  
    System.out.println("Hello world!");

    double eggPrice = 2.50;
    double money = 2.50;

    // If eggs cost less than 3 euros
    //   Then buy them
    // Else
    //   Don't buy them
    
    if (eggPrice >= money) {
      // = always after the > or <
      // == is for comparing
      System.out.println("Go work!");
    } else {
      System.out.println("Buy the eggs");
    }

        System.out.println("This code is going to show always");
  }

public class Main {
  public static void main(String[] args) {


    System.out.println("Hello world");
    System.out.println(5);
    System.out.println("Hello WoTech");
var name = "Anna";
    System.out.println(name);
    System.out.println("2" + "2");
    System.out.println(2 + 2);

    // This is a string

    var text = "This is a random text";
    text = "this is another text";
    text = "asd";
    text = "March ";

    //boolean
    var isDisabled = false;
    isDisabled = true; 

    var gameOver = false;
    gameOver = true;

    var clientIsActive = true; 
    clientIsActive = false;

    //integer 
    var number = 5;
    number = number + 7;

    //float, character
    var interestingNumber = 100.5;
    var mixedInterestingNumber = number + interestingNumber;

    //Can't combine mixedInterestingNumber + number under var number. 

    number = number * 3;
    number = number / 3;



    System.out.println(text);
    System.out.println(isDisabled);
    System.out.println(gameOver);
    System.out.println(clientIsActive);
    System.out.println(number);
    System.out.println(interestingNumber);
    System.out.println(mixedInterestingNumber);
    System.out.println(number);
  }}

import java.util.Scanner;

public class LoginApplication {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        final String STORED_USERNAME = "user123";
        final String STORED_PASSWORD = "pass123";

        System.out.print("input your username: ");
        String username = scanner.nextLine();

        System.out.print("input your password: ");
        String password = scanner.nextLine();

        if (username.equals(STORED_USERNAME) && password.equals(STORED_PASSWORD)) {
            System.out.println("you have access");
        } else {
            System.out.println("username or password is invalid");
        }

        scanner.close();
    }
}

```
