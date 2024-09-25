# MATH

## MathService
```java
package com.example;

public class MathService {
    public int getSum(int a, int b) {
        int result = a + b;
        if (result > 100) {
            return 0;
        }
        return result;
    }
}
```

## MathServiceTests
```java
package com.example;

import org.junit.jupiter.api.Test;
import org.springframework.util.Assert;

public class MathServiceTests {
    @Test
    void WHEN_SumBelowHundred_THEN_Result_Sum() {
        var mathService = new MathService();
        var sum = mathService.getSum(1, 2);
        Assert.isTrue(sum == 3,  "Hey, the sum should be the result. Unless the sum exceeds hundred.");
    }
    @Test
    void WHEN_SumOverHundred_THEN_Result_Zero() {
        var mathService = new MathService();
        var sum = mathService.getSum(100,2);
        Assert.isTrue(sum == 0,  "Hey, the sum exceeds hundred.");
    }
}
```

# GAME
## GameService
```java
package com.datorium.Datorium.API;

public class Game {

    private int number;

    public void setNumber(int number) {
        this.number = number;
    }

    public int takeAGuess(int guess) {
        if (guess > number) {
            return 3;
        } else if (guess < number) {
            return 2;
        } else {
            return 1;
        }
    }
}
```

## GameServiceTests
```java
package com.datorium.Datorium.API;

import org.junit.jupiter.api.Test;
import org.springframework.util.Assert;

public class GameTests {

        @Test
        void GIVEN_ItIsTooBig_WHEN_CallingGame_THEN_ReturnFalse() {

                //Arrange
                var game = new Game();
                game.setNumber(5);
                //Act
                var response = game.takeAGuess(20);
                //Assert
                Assert.isTrue(response == 3, "It's supposed to be 3");
        }

        @Test
        void GIVEN_ItIsTooSmall_WHEN_CallingGame_THEN_ReturnFalse() {

                //Arrange
                var game = new Game();
                game.setNumber(5);
                //Act
                var response = game.takeAGuess(2);
                //Assert
                Assert.isTrue(response == 2, "It's supposed to be 2");
        }

        @Test
        void GIVEN_ItIsEqual_WHEN_CallingGame_THEN_ReturnFalse() {

                //Arrange
                var game = new Game();
                game.setNumber(5);
                //Act
                var response = game.takeAGuess(5);
                //Assert
                Assert.isTrue(response == 1, "It's supposed to be 1");
        }
}
```
# DATE
## DateService
```java
package com.example;

import java.util.Calendar;

public class DateService {
    public boolean isWeekend(Calendar calendar){
        //1. Get the date --> day
        //2. Check whether or not this day is Saturday or Sunday
        //3. Import calendar
        //4. Return boolean

        var currentDay = calendar.get(Calendar.DAY_OF_WEEK);

        return(currentDay==Calendar.SATURDAY || currentDay==Calendar.SUNDAY);
    }
}
```

## DateServiceTests
```java
package com.example;

import org.junit.jupiter.api.Test;
import org.springframework.util.Assert;

import java.util.Calendar;

public class DateServiceTests {

    @Test
    void GIVEN_ItIsThursday_WHEN_CallingIsWeekend_THEN_ReturnFalse(){
        //Arrange
        var dateService = new DateService();
        Calendar calendar = Calendar.getInstance();
        calendar.set(2024, Calendar.SEPTEMBER, 19);
        //Act
        var isWeekend = dateService.isWeekend(calendar);

        //Assert
        Assert.isTrue(!isWeekend, "This was not supposed to be a weekend!");
    }
    @Test
    void GIVEN_ItIsSaturday_WHEN_CallingIsWeekend_THEN_ReturnTrue(){
        //Arrange
        var dateService = new DateService();
        Calendar calendar = Calendar.getInstance();
        calendar.set(2024, Calendar.SEPTEMBER, 21);
        //Act
        var isWeekend = dateService.isWeekend(calendar);

        //Assert
        Assert.isTrue(isWeekend, "This is weekend!");
    }
    @Test
    void GIVEN_ItIsSunday_WHEN_CallingIsWeekend_THEN_ReturnTrue(){
        //Arrange
        var dateService = new DateService();
        Calendar calendar = Calendar.getInstance();
        calendar.set(2024, Calendar.SEPTEMBER, 22);
        //Act
        var isWeekend = dateService.isWeekend(calendar);

        //Assert
        Assert.isTrue(isWeekend, "This is weekend!");
    }
}
```

# TEST EXAMPLE
## TestExampleApplication
```java
package com.example;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
//import org.springframework.web.bind.annotation.CrossOrigin;
//import org.springframework.web.bind.annotation.GetMapping;

@SpringBootApplication
//@RestController
//@CrossOrigin
public class TestExampleApplication {

	public static void main(String[] args) {
		var userService = new UserService();

		String name;
		System.out.println(userService.getFullName("Kristiina", "Li"));

		var mathService = new MathService();

		System.out.println(mathService.getSum(1, 2));
		SpringApplication.run(TestExampleApplication.class, args);
	}

}
```

## TestExampleApplicationTests
```java
package com.example;

import org.junit.jupiter.api.Test;
import org.springframework.boot.test.context.SpringBootTest;
import org.springframework.util.Assert;

@SpringBootTest
class TestExampleApplicationTests {

	@Test
	void WHEN_NameIsOskarsAndSurnameIsKlaumanis_THEN_Result_Oskars_Klaumanis() {
		// Hard code your unit test to have it as straight forward as possible
		// Arrange -> prepare data and services
		var userService = new UserService();

		// Act -> Do some action, usually call a method
		var fullname = userService.getFullName("Kristiina", "Li");

		// Assert -> Test whether or not the result is correct
		Assert.isTrue(fullname.equals("Kristiina Li"), "Hey, the name should be with a space in between and should contain both name and surname");
	}
	//Unit test naming convention java
	// What we receive, what we do, and what we return
	// WHEN_NameIsKristiinaAndSurnameIsLi_THEN_ResultKristiinaLi
}
```

