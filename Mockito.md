# Teamwork CityLottery

## City.java
```java
package com.datorium.Datorium.API.CityLottery;

public class City {
    private String name;
    private int population;

    public City(String name, int population) {
        this.name = name;
        this.population = population;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getPopulation() {
        return population;
    }

    public void setPopulation(int population) {
        this.population = population;
    }
}
```

## CityRepository.java
```java
package com.datorium.Datorium.API.CityLottery;

import java.util.ArrayList;

public class CityRepository implements ICityRepository {

    // mock DB
    public ArrayList<City> getCities() {
        // prepare list of cities --> Repo
        // mock list of cities before DB is used
        ArrayList<City> cities = new ArrayList<City>();
        City goog = new City("Goog", 75);
        City wocity = new City("WoCity", 25);
        //City banteer = new City("Banteer", 230);
       // City pori = new City("Pori", 145);
        cities.add(goog);
        cities.add(wocity);
       // cities.add(banteer);
       // cities.add(pori);

        return cities;
  ```

## CityService.java
```java
package com.datorium.Datorium.API.CityLottery;

import java.util.ArrayList;
import java.util.Random;

public class CityService {

    // 1. Count total amount of citizens -> 100
    // 2. Choose random number -> 56
    // 3. Loop going through all the cities
    // 4. Choose the city with the correct lottery number

    private ICityRepository cityRepository;
    public CityService(ICityRepository cityRepository) {
        this.cityRepository = cityRepository;
    }

    public City getRandomCity(ICityRepository cityRepo, Random random) {
        ArrayList<City> cities = cityRepo.getCities();
        int totalCitizenCount = getTotalCitizens(cityRepo);
        int randomNumber = getRandomNumber(totalCitizenCount, random);
        City winner = getCity(cities, randomNumber);
        return winner;
    }

    private int getTotalCitizens(ICityRepository cityRepo) {
        ArrayList<City> cities = cityRepo.getCities();
        int totalCitizenCount = 0;
        for (City city : cities) {
            totalCitizenCount += city.getPopulation();
        }
        return totalCitizenCount;
    }

    private int getRandomNumber(int totalCitizenCount, Random random) {
        // 2. Choose random number from 0 (inclusive) to 100 (exclusive)
        int randomNumber = random.nextInt(totalCitizenCount);
        return randomNumber;
    }

    private City getCity(ArrayList<City> cities, int random) {
        // 3. Loop going through all the cities
        // 4. Choose the city with the correct lottery number
        // population --> 75
        // randomNumber --> 56
        // subtract 56 - 25 (wocity) = 31 --> positive number
        // BECAUSE IT IS NOT BELOW OR EQUAL TO 0, GO TO NEXT CITY POPULATION
        // 31 - 75 --> THIS IS BELOW 0, we choose this city
        City winnerCity = null;
        for (City city : cities) {
            random -= city.getPopulation();
            if (random <= 0) {
                winnerCity = city;
            }
        }
        return winnerCity;
    }
}
```

## CityServiceTests.java
```java
package com.datorium.Datorium.API;

import com.datorium.Datorium.API.CityLottery.City;
import com.datorium.Datorium.API.CityLottery.CityRepository;
import com.datorium.Datorium.API.CityLottery.CityService;
import com.datorium.Datorium.API.CityLottery.ICityRepository;
import org.junit.jupiter.api.Test;
import org.mockito.Mockito;
import org.springframework.util.Assert;

import java.util.ArrayList;
import java.util.Random;

import static org.junit.jupiter.api.Assertions.assertEquals;

public class CityServiceTests {

    // when there is goog and wocity
    // goog has 10%
    // wocity has 90%
    // randomizer chooses 9
    // choose goog

    @Test
    public void GIVEN_Goog10_Wocity90_WHEN_Random9_THEN_Choose_Goog(){
        // Arrange
        // create a mock repository
        ICityRepository cityRepository = Mockito.mock(ICityRepository.class);

        // Define two cities, Goog and Wocity, with their respective probabilities
        City goog = new City("Goog", 10);
        City wocity = new City("Wocity", 90);

        // Mock the behavior of the repository to return these cities
        ArrayList<City> cities = new ArrayList<City>();
        cities.add(wocity);
        cities.add(goog);
        Mockito.when(cityRepository.getCities()).thenReturn(cities);

        // Create the CityService with the mocked repository
        CityService cityService = new CityService(cityRepository);

        // Mock the randomizer to return a value of 9
        Random random = Mockito.mock(Random.class);
        Mockito.when(random.nextInt(100)).thenReturn(9);

        // Act
        City winnerCity = cityService.getRandomCity(cityRepository, random);

        // Assert
        //Assert.isTrue(winnerCity.equals("Goog"));
        //Assert.isTrue(goog.getName().equals(winnerCity.getName()) && goog.getPopulation() == winnerCity.getPopulation());
        Assert.isInstanceOf(winnerCity.getClass(), "Goog");

    }
}
```

## DatoriumAPIApplication.java ### I have TestExampleApplication which mean that a lot of the references should be changed!!!
```java
package com.datorium.Datorium.API;

import com.datorium.Datorium.API.CityLottery.City;
import com.datorium.Datorium.API.CityLottery.CityRepository;
import com.datorium.Datorium.API.CityLottery.CityService;
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.web.bind.annotation.CrossOrigin;
import org.springframework.web.bind.annotation.RestController;

import java.util.Random;

@SpringBootApplication
@RestController
@CrossOrigin
public class DatoriumApiApplication {

	public static void main(String[] args) {

		Random random = new Random();
		CityService cityService = new CityService(new CityRepository());
		CityRepository cityRepository = new CityRepository();
		City winner = cityService.getRandomCity(cityRepository, random);
		System.out.println(winner.getName());

		/*UserService userService = new UserService();
		MathService mathService = new MathService();

		System.out.println(userService.getFullName("Laila", "Duffy"));
		System.out.println(mathService.sum(5, 78));*/

		SpringApplication.run(DatoriumApiApplication.class, args);
	}
}
```

## ICityRepository.java
```java
package com.datorium.Datorium.API.CityLottery;

import java.util.ArrayList;

public interface ICityRepository {
    public ArrayList<City> getCities();
}
```
