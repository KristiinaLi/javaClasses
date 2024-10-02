# CityLottery

## City.java
```java
package com.example.CityLottery;

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

    public int getPopulation() {
        return population;
    }
}
```

## CityService.java
```java
package com.example.CityLottery;
import java.util.Random;

public class CityService {

    private ICityRepository cityRepository;
    private int seed;
    public CityService(ICityRepository cityRepository, int seed){
        this.cityRepository = cityRepository;
        this.seed = seed;
    }

    public CityService(ICityRepository cityRepository){
        this.cityRepository = cityRepository;
    }
    /*
     * 0. Prepare a list of cities
     * 1. Count total amount of citizens -> 100
     * 2. Choose random number -> 56
     * 3. Loop going through all of the cities
     * 4. Choose the city with correct lottery ticket
     * */

    public City getRandomCity() throws Exception {
        var cities = cityRepository.getCities();
        //1. Count total amount of citizens -> 100
        var totalCitizenCount = 0;
        for (City city: cities){
            totalCitizenCount += city.getPopulation();
        }
        //2. Choose random number -> 56
        // If we have seed, then random = new Random(seed) else random = new Random()
        Random random = (seed != 0)
                ? new Random(seed)
                : new Random();

        int randomValue = random.nextInt(totalCitizenCount);

        //3. Loop going through all of the cities
        //4. Choose the city with correct lottery ticket
        //population -> 25
        //randomValue -> 56
        //We subtract 56 - 25 = 31
        // BECAUSE ITS NOT BELOW OR EQUAL TO 0, GO TO NEXT
        // 31 - 75 -> because it's below 0, we choose this city
        for(City city: cities){
            randomValue -= city.getPopulation();

            if(randomValue <= 0){
                return city;
            }
        }
        throw new Exception("Something wrong");
    }
}
```

## ICityRepository.java
```java
package com.example.CityLottery;

import java.util.ArrayList;

public interface ICityRepository {
    ArrayList<City> getCities();
    // no implementations in Interface, just declaration
    // This is an abstract class
    //
}
```

## CityServiceTest.java
```java
import com.example.CityLottery.City;
import com.example.CityLottery.CityRepository;
import com.example.CityLottery.CityService;
import com.example.CityLottery.ICityRepository;
import org.junit.jupiter.api.Test;
import org.mockito.Mockito;
import org.springframework.util.Assert;

import java.util.ArrayList;
import java.util.Random;

import static org.junit.jupiter.api.Assertions.assertEquals;

import static org.mockito.Mockito.when;

public class CityServiceTests {

    // when there is goog and wocity
    // goog has 10% (10 citizens)
    // wocity has 90% (90 citizens)
    // randomizer chooses 9
    // choose goog

    @Test
    public void Given_Goog83_Wocity17_When_Randomizer82_Then_ChooseGoog() throws Exception {

        //Arrange
        // 1. CityService needs cityRepository in the constructor
        // 2. Make a fake cityRepository
        // Instead of using db, we are using fake data
        var cityRepository = Mockito.mock(ICityRepository.class);

        // 3. Create a city service, by providing fake repository
        // 4. Add a seed for the city service, that gives us repeatable result
        var cityService = new CityService(cityRepository, 123);

        // 5. Create a list of fake cities
        var cities = new ArrayList<City>();

        // 6. Add fake cities, to our fake city list
        cities.add(new City("Goog", 83));
        cities.add(new City("Wocity", 17));

        // WHEN someone asks db for cities
        // THEN return predetermined cities
        // 7. Set it up, that when we want to get cities
        // we actually get these fake cities prepared in point 6
        when(cityRepository.getCities()).thenReturn(cities);

        // Act
        var randomCity = cityService.getRandomCity();

        //Assert
        Assert.isTrue(randomCity.getName().equals("Goog"), "Goog is supposed to be chosen!");
    }
}
```

## CityRepository.java
```java
package com.example.CityLottery;

import java.util.ArrayList;

public class CityRepository implements ICityRepository { //Standardization
    //mock db

    public ArrayList<City> getCities(){  //This is declaration
        // 0. Prepare a list of cities
        ArrayList<City> cities = new ArrayList<>(); // Everything inside {} is implementation
        var goog = new City("Goog",75);
        var wocity = new City("Wocity",25);
        var oskarscity = new City("Oskars city",25);
        cities.add(goog);
        cities.add(wocity);
        cities.add(oskarscity);
        return cities;
    }
}
```

## TestExampleApplication.java
```java
package com.example;
import com.example.CityLottery.City;
import com.example.CityLottery.CityRepository;
import com.example.CityLottery.CityService;
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.web.bind.annotation.CrossOrigin;
import org.springframework.web.bind.annotation.RestController;

import java.util.Random;

@SpringBootApplication
@RestController
@CrossOrigin
public class TestExampleApplication {

	public static void main(String[] args) throws Exception {
		var cityService = new CityService(new CityRepository());
		var randomCity = cityService.getRandomCity();
		System.out.println(randomCity.getName());

	}
}
```
