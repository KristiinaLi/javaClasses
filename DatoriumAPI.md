# Datorium API

```java
package com.datorium.Datorium.API;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.web.bind.annotation.CrossOrigin;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestParam;
import org.springframework.web.bind.annotation.RestController;

@SpringBootApplication
@RestController
@CrossOrigin
public class DatoriumApiApplication {

	public static void main(String[] args) {
		System.out.println("asd");
		SpringApplication.run(DatoriumApiApplication.class, args);
	}


	@GetMapping("/ping")
	public String ping() {
		return "pong";
	}

	@GetMapping("/hello")
	public String hello(@RequestParam(value = "name", defaultValue = "World") String name) {
		return String.format("Hello %s!", name); // "Hello " + name + "!";
	}

	@GetMapping("/sum")
	public int sum(@RequestParam(value = "number1") int number1, @RequestParam(value = "number2") int number2){
	return number1 + number2;
	}

	@GetMapping("/multiply")
	public int multiply(@RequestParam(value = "number1") int number1, @RequestParam(value = "number2") int number2){
		return number1 * number2;
	}

	@GetMapping("/divide")
	public int divide(@RequestParam(value = "number1") int number1, @RequestParam(value = "number2") int number2){
		return number1 / number2;
	}

	@GetMapping("/draw")
	public int[][] draw(){
		return new int[][]{
				new int[]{0, 1, 1},
				new int[]{1, 0, 1},
				new int[]{1, 1, 0}};
	}

	@GetMapping("/Birthdays")
	public String [] birthdays (){
		String [] birthdays = new String [4];
		birthdays[0] = "20.02";
		birthdays[1] = "13.08";
		birthdays[2] = "04.06";
		birthdays[3] = "20.04";
		return birthdays;
	}

	@GetMapping("/draw2")
	public int[][] draw2(){
		return new int[][]{
				new int[]{0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0},
				new int[]{1, 0, 0, 0, 0, 0, 1, 0, 1, 1, 1, 1, 1, 1, 1},
				new int[]{1, 1, 0, 0, 0, 1, 1, 0, 1, 0, 0, 0, 0, 0, 1},
				new int[]{0, 1, 0, 1, 0, 1, 0, 0, 1, 0, 0, 0, 0, 0, 1},
				new int[]{0, 1, 0, 1, 0, 1, 0, 0, 1, 0, 0, 0, 0, 0, 1},
				new int[]{0, 1, 1, 1, 1, 1, 0, 0, 1, 0, 0, 0, 0, 0, 1},
				new int[]{0, 0, 1, 0, 1, 0, 0, 0, 1, 0, 0, 0, 0, 0, 1},
				new int[]{0, 0, 1, 0, 1, 0, 0, 0, 1, 1, 1, 1, 1, 1, 1},
				new int[]{0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0},
				new int[]{1, 1, 1, 0, 1, 1, 1, 0, 1, 1, 1, 0, 1, 0, 1},
				new int[]{0, 1, 0, 0, 1, 0, 0, 0, 1, 0, 1, 0, 1, 0, 1},
				new int[]{0, 1, 0, 0, 1, 1, 0, 0, 1, 0, 0, 0, 1, 1, 1},
				new int[]{0, 1, 0, 0, 1, 0, 0, 0, 1, 0, 1, 0, 1, 0, 1},
				new int[]{0, 1, 0, 0, 1, 1, 1, 0, 1, 1, 1, 0, 1, 0, 1},
				new int[]{0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0}};
	}

	@GetMapping("/draw3")
	public int[][] draw3() {
		return new int[][]{
				new int[]{0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0},
				new int[]{0, 0, 0, 0, 1, 1, 1, 0, 0, 0, 0, 0, 0, 0, 1, 1, 1, 0, 0, 0, 0},
				new int[]{0, 0, 0, 1, 1, 1, 1, 1, 0, 0, 0, 0, 0, 1, 1, 1, 1, 1, 0, 0, 0},
				new int[]{1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1},
				new int[]{0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0},
				new int[]{0, 0, 1, 0, 0, 0, 0, 1, 1, 1, 0, 1, 1, 1, 0, 0, 0, 0, 1, 0, 0},
				new int[]{0, 0, 0, 1, 0, 0, 0, 1, 1, 1, 0, 1, 1, 1, 0, 0, 0, 1, 0, 0, 0},
				new int[]{0, 0, 0, 0, 1, 0, 0, 1, 1, 1, 0, 1, 1, 1, 0, 0, 1, 0, 0, 0, 0},
				new int[]{0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0},
				new int[]{0, 0, 0, 0, 0, 0, 1, 0, 0, 1, 1, 1, 0, 0, 1, 0, 0, 0, 0, 0, 0},
				new int[]{0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 1, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0},
				new int[]{0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0},
				new int[]{0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0},
				new int[]{0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0}};
	}
}

```

## Second step
```java
package com.datorium.Datorium.API;

import com.datorium.Datorium.API.DTO.Book;
import com.datorium.Datorium.API.DTO.Credentials;
import com.datorium.Datorium.API.DTO.User;
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.web.bind.annotation.*;

@SpringBootApplication
@RestController
@CrossOrigin
public class DatoriumApiApplication { // Main class - app starting

	public static void main(String[] args) {
		System.out.println("asd");
		SpringApplication.run(DatoriumApiApplication.class, args);
	}


	@GetMapping("/ping")
	public String ping() {
		return "pong";
	}

	@GetMapping("/hello")
	public String hello(@RequestParam(value = "name", defaultValue = "World") String name) {
		return String.format("Hello %s!", name);
	}

	@GetMapping("/sum")
	public int sum(@RequestParam(value = "number1") int number1, @RequestParam(value = "number2") int number2){
	return number1 + number2;
	}

	@GetMapping("/multiply")
	public int multiply(@RequestParam(value = "number1") int number1, @RequestParam(value = "number2") int number2){
		return number1 * number2;
	}

	@GetMapping("/divide")
	public int divide(@RequestParam(value = "number1") int number1, @RequestParam(value = "number2") int number2){
		return number1 / number2;
	}

	@GetMapping("/getbook")
	public Book getBook(){
		var book = new Book();
		book.title = "Book Title";
		book.author = "Book Author";

		return book;
	}

	@PostMapping("/postexample")
	public Book addBook(@RequestBody Book book){
		book.title = book.title.toUpperCase();
		return book;
	}

	@PostMapping("/authorize")
	public User authorize(@RequestBody Credentials credentials){ // username + password
		if(credentials.username.equals("okklv") && credentials.password.equals("Password123")){
			var user = new User();
			user.name = "Oskars";
			return user;
		}
		return null;

	}
	// We want the user to be able to authorize by using username and password
	// And then we provide a profile of the user (name, surname, age, e-mail)
}
```

# Going further
![image (3)](https://github.com/user-attachments/assets/addf549c-5541-494b-9b81-c5553784139c)

Repo goes back and forth to/from Database; same functions as controller

CRUD = Creat, Read, Update, Delete

## Encapsulation
Encapsulation in Java is a fundamental concept in object-oriented programming (OOP) that refers to the bundling of data and methods that operate on that data within a single unit, which is called a class in Java. Java Encapsulation is a way of hiding the implementation details of a class from outside access and only exposing a public interface that can be used to interact with the class.

In Java, encapsulation is achieved by declaring the instance variables of a class as private, which means they can only be accessed within the class. To allow outside access to the instance variables, public methods called getters and setters are defined, which are used to retrieve and modify the values of the instance variables, respectively. By using getters and setters, the class can enforce its own data validation rules and ensure that its internal state remains consistent.

We want to keep it secure, as stable as it can be: Controller --> Service --> Repo --> DB
If another service accesses Service from the side, and this continues as a long chain.
We don't want anyone to use the same object. Every service is going to have their own repository, and own connection to DB. 
