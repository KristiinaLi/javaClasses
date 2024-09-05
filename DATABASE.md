# DATABASE

```SQL
-- DROP TABLE persons
CREATE table persons 

(id INTEGER PRIMARY KEY AUTOINCREMENT, name varchar(20));
```

Primary key == the value is unique. You might want to have an ID number that is unique for a user. 
varchar == string (just a text); we can add a limitation to avoid huge amounts of input.
Autoincrement == automation of creation of numbers (new ID numbers). It is never reusing IDs. Once the ID is deleted, autoincrement takes the next available number. 
DROP table persons == when something goes wrong, you can start over

```SQL
INSERT INTO persons (name) VALUES (
  'oskars'
  );
  
select * FROM persons
```

In order to RUN only a part of the code, highlight the code you want to run, and press RUN.

ORM

%appdata% to computer search field. Find JetBrains and delete it to clear problems with IntelIJ IDEA. 

# 29.09

Try/Catch
Using try/catch allows your program to handle errors gracefully without crashing. Instead of stopping, the program can take specific actions when an error happens, like showing an error message to the user or trying an alternative approach.

The try/catch concept in Java is used for handling exceptions, which are errors that can occur during the execution of a program.

Basic Idea:

try block: You put the code that might cause an exception (error) inside this block. This is like saying, "Try to execute this code." (Use it to wrap code that might cause an exception.)

catch block: If an exception occurs in the try block, the program will jump to this block. It's like saying, "If something goes wrong, catch the problem here and handle it." (Use it to define how to handle the exception if it occurs.)

In Java, you can catch multiple different types of exceptions, but each catch block is designed to handle a specific type of exception. However, Java allows you to use multiple catch blocks after a single try block, so you can handle different types of exceptions differently.

Code from the lesson
import java.sql.DriverManager;
import java.sql.SQLException;
import java.util.Scanner;


public class Main {

    public static void main(String[] args) {
        var sc = new Scanner(System.in);

        //we ask the user for their name
        System.out.println("Please provide your name: ");
        var personsName = sc.nextLine();

        String url = "jdbc:sqlite:my.db";
        try (var conn = DriverManager.getConnection(url)) {
            if (conn != null) {
                var statement = conn.createStatement();
                statement.execute("INSERT INTO people (name) VALUES ('" + personsName +"')");
            }
        } catch (SQLException e) {
            System.err.println(e.getMessage());
        }
    }
}
Some reading material from Oskars about SQL injection - https://portswigger.net/web-security/sql-injection
TEAMWORK
Use the example of SQL in Java and add an "AddUser" method inside the previous Datorium API project - UserRepository. Try and run Postman and verify with DB Browser that the data is there.

1. UserRepo.java
```java
package com.datorium.Datorium.API.Repo;

import com.datorium.Datorium.API.DTO.User;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.util.ArrayList;
import java.util.Scanner;

public class UserRepo { // used for users, don't use "user" as part of the function's name.

   private ArrayList<User> users = new ArrayList<>(); // Mocked database

   public int add(User user){ // hold ctrl and add left click on mouse to see the original
       users.add(user);
       return users.size();
   }
   public ArrayList<User> getUsers(){
       return users;
   } // returning the users from the private property, privet ArrayList;

   public User update(int userIndex, User updateUserDTO){ // this user is never going to exist in database, but we use this DTO, to update the actual entities in database
       var user = users.get(userIndex); // getting user from ArrayList
       user.name = updateUserDTO.name;
       return user;
   }

   // User user = type, name of the variable
   public String addUser(User user) {
       String url = "jdbc:sqlite:my.db";  // Update this to your actual database name

       try (var conn = DriverManager.getConnection(url)) { // Create a connection
           if (conn != null) { // If connection exists, do things with connection, e.g. send query
               var statement = conn.createStatement();
               statement.execute("CREATE TABLE people (id INTEGER PRIMARY KEY AUTOINCREMENT, name varchar(20))");
               statement.execute("INSERT INTO people (name) VALUES ('" + user.name + "')");
               return "User " + user.name + " added successfully";  // Return a success message
           }
       } catch (SQLException e) {
           System.err.println(e.getMessage());
           return "Failed to add user: " + e.getMessage();  // Return an error message
       }
       return null;  // This should generally not be reached if the connection was successful
   }
}
```

UserController.java
```java
package com.datorium.Datorium.API.Controllers;

import com.datorium.Datorium.API.DTO.UpdateUserDTO;
import com.datorium.Datorium.API.DTO.User;
import com.datorium.Datorium.API.Repo.UserRepo;
import com.datorium.Datorium.API.Services.UserService;
import org.springframework.web.bind.annotation.*;

import java.util.ArrayList;

@RestController
@RequestMapping("/user")
public class UserController {

    private UserService userService;
    public UserController(){
        // This code runs first, when creating UserController object
        userService = new UserService();
    }
    //CRUD
    //AddUser
    //UpdateUser
    //GetUser
    //DeleteUser

    @PostMapping("/add") //localhost:8080/test -> localhost:8080/user/test
    public int add(@RequestBody User user) {
        return userService.add(user);
    }

    @GetMapping ("/get")
    public ArrayList<User> get() {
        return userService.getUsers();
    }

    @PostMapping ("/update")
    public User update(@RequestBody UpdateUserDTO updateUserDTO) {
        return userService.update(updateUserDTO.userIndex, updateUserDTO.user); }

    @PostMapping ("/addUser")
    public String addUser(@RequestBody User user) {return userService.addUser(user); }
}
```

UserService.java
```java
// Business logic
package com.datorium.Datorium.API.Services;
import com.datorium.Datorium.API.DTO.User;
import com.datorium.Datorium.API.Repo.UserRepo;
import java.util.ArrayList;

public class UserService {
    private UserRepo userRepo;

    public UserService() { // we want to connect to the server; userService checks if the user is real; if the username us already in use
        userRepo = new UserRepo();
    }
    public int add(User user){
        return userRepo.add(user);
    }
    public ArrayList<User> getUsers(){
        return userRepo.getUsers();
    }
    public User update(int userIndex, User updateUserDTO){
        return userRepo.update(userIndex, updateUserDTO);
    }
    public String addUser(User user){ return userRepo.addUser(user); }
}
```

# 05.09.2024
UserController.java
```java
package com.datorium.Datorium.API.Controllers;

import com.datorium.Datorium.API.DTOs.UpdateUserDTO;
import com.datorium.Datorium.API.DTOs.User;
import com.datorium.Datorium.API.Services.UserService;
import org.springframework.web.bind.annotation.*;
import org.apache.coyote.BadRequestException;

import java.util.ArrayList;

@RestController
@RequestMapping("/user")
public class UserController {
    private UserService userService;
    public UserController(){
        userService = new UserService();
    }
    //CRUD
    //AddUser
    //UpdateUser
    //GetUser
    //DeleteUser

    //@GetMapping
    @PostMapping("/add") //localhost:8080/user/add
    public void add(@RequestBody User user) throws BadRequestException {
        userService.add(user);
    }

    @GetMapping("/get")
    public ArrayList<User> get(){
        return userService.get();
    }

    @PostMapping("/update")
    public User update(@RequestBody UpdateUserDTO updateUserDTO){
        return userService.update(updateUserDTO.userIndex, updateUserDTO.user);
    }
}
```

UserService.java
```java
package com.datorium.Datorium.API.Services;

import com.datorium.Datorium.API.DTOs.User;
import com.datorium.Datorium.API.Repo.UserRepo;
import org.apache.coyote.BadRequestException;

import java.util.ArrayList;

// Business logic

public class UserService {
    private UserRepo userRepo;

    public UserService() {
        userRepo = new UserRepo();
    }

    public void add(User user) throws BadRequestException {
        if (user.name.isEmpty()){
            throw new BadRequestException("Name cannot be empty");
        }
        userRepo.add(user);
    }

    public ArrayList<User> get(){
        return userRepo.get();
    }

    public User update(int userIndex, User updateUserDTO){
        return userRepo.update(userIndex, updateUserDTO);
    }
}
```

UserRepo.java
```java
package com.datorium.Datorium.API.Repo;

import com.datorium.Datorium.API.DTOs.User;

import java.sql.DriverManager;
import java.sql.SQLException;
import java.util.ArrayList;

public class UserRepo {

    private ArrayList<User> users = new ArrayList<>();//Mocked db

    public void add(User user) {
        String url = "jdbc:sqlite:my.db";
        try (var conn = DriverManager.getConnection(url)) {
            if (conn != null) {
                var statement = conn.createStatement();
                statement.execute("INSERT INTO people (name) VALUES ('" + user.name + "')");
                //INSERT INTO people (name) VALUES ('');DROP TABLE people;--')
            }
        } catch (SQLException e) {
            System.err.println(e.getMessage());
        }
    }

    public ArrayList<User> get(){
        String url = "jdbc:sqlite:my.db"; // LOCATION OF database
        var resultList = new ArrayList<User>(); // Create a list = prepare a box where to put the users
        try (var conn = DriverManager.getConnection(url)) { // Connection is made
            if (conn != null) { // Connection is not null
                var statement = conn.createStatement(); // Create action what to do
                var result = statement.executeQuery("SELECT name FROM people"); // Select all the names from table people
                //Different Box, but more abstract; once we see one element, we cannot see it again
                //Kind of like an array, list; never null, but can be empty;
                while(result.next()){ // Going through abstract box
                    var user = new User(); // Create new user
                    user.name = result.getString("name"); // assign name to the new user
                    resultList.add(user); // Add user to the box
                    //While loop stops where there is no next element
                }
            }
        } catch (SQLException e) {
            System.err.println(e.getMessage());
        }
        return resultList;
    }

    public User update(int numberOfChristmasPresents, User updateUserDTO){
        var user = users.get(numberOfChristmasPresents);
        user.name = updateUserDTO.name;
        return user;
    }
}
```

User.java
```java
package com.datorium.Datorium.API.DTOs;

public class User {
    public String name;
}
```
