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
