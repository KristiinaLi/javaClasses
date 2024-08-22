# SQLite

# First lesson - FILTERING

Find all pets that are older than 5 years:
```SQL
SELECT FROM Pets WHERE Age > 5;
```
Find all owners living in a specific city:
```SQL
SELECT * FROM Owners WHERE City = 'Detroit';
```
Find all procedures that cost more than $100:
```SQL
SELECT * FROM Procedures WHERE Price > 100;
```
Multiple Filters
Find male pets that are older than 3 years:
```SQL
SELECT FROM Pets WHERE Sex = 'male' AND Age > 3;
```
Find owners who live in a particular state and city:
```SQL
SELECT * FROM Owners WHERE State = 'MI' AND City = 'Livonia';
```
Find procedures with a specific type and price range:
```SQL
SELECT * FROM Procedures WHERE ProcedureType = ' ORTHOPEDIC' AND Price BETWEEN 200 AND 500;
```
*Using JOINs and Filters
Find all pets along with their owners' details:
```SQL
SELECT Pets.Name, Pets.Kind, Owners.Name, Owners.Surname
FROM Pets
JOIN Owners ON Pets.OwnerID = Owners.OwnerID;
```
Find owners who have pets of a particular kind (e.g., dogs):
```SQL
SELECT Owners.Name, Owners.Surname
FROM Owners
JOIN Pets ON Owners.OwnerID = Pets.OwnerID
WHERE Pets.Kind = 'Dog';
```
Combining Filters with Aggregates
Find the average age of all pets in the database:
```SQL
SELECT AVG(Age) AS AverageAge FROM Pets;
```
Find the number of procedures that cost more than $150:
```SQL
SELECT COUNT() AS ExpensiveProcedures FROM Procedures WHERE Price > 150; Using LIKE for Pattern Matching
```
Find all owners whose surname starts with 'S':
```SQL
SELECT FROM Owners WHERE Surname LIKE 'S%';
```
Find all pets with names that end in 'y':
```SQL
SELECT * FROM Pets WHERE Name LIKE '%y';
```
Using IN and NOT IN
Find all pets that are not dogs or cats:
```SQL
SELECT FROM Pets WHERE Kind NOT IN ('Dog', 'Cat');
```
Using BETWEEN and Date Filters
Find all procedures performed between two dates:
```SQL
SELECT FROM Sales WHERE Date BETWEEN '06/03/2018' AND '26/05/2019';
```
Find all pets that are between 2 and 8 years old:
```SQL
SELECT * FROM Pets WHERE Age BETWEEN 2 AND 8; 

SELECT * FROM Pets WHERE LENGTH(Name) = 5;
SELECT * FROM Pets WHERE Name LIKE '%er';
SELECT DISTINCT Kind FROM Pets;
```

How many diferent type of pets there are?
```SQL
SELECT kind, COUNT(*) AS Count 
FROM Pets 
GROUP BY Kind
ORDER BY Count DESC;
```
What is the most popular pet name? 
```SQL
SELECT Name, COUNT(*) AS Count 
FROM Pets 
GROUP BY Name
ORDER BY Count DESC;
```
What is most common pet age?
```SQL
SELECT Age, COUNT(*) AS Count
FROM Pets
GROUP BY Age
ORDER BY Count DESC
LIMIT 1;
```
What are the top 3 longest pet names?
``SQL
SELECT *
FROM Pets 
ORDER BY LENGTH(Name) DESC
LIMIT 3;
```
What is the biggest number of pets an owner has? 
```SQL
SELECT OwnerID, COUNT(*) AS PetCount
FROM Pets
GROUP BY OwnerID
ORDER BY PetCount DESC
LIMIT 1;
```

What is the avarage age of the previous owners pets? 
```SQL
SELECT AVG(Age) AS AverageAge
FROM Pets
WHERE OwnerID = 4782;
```
Filtering by Exact Match - pets, who are male
```SQL
SELECT * FROM Pets WHERE Sex = 'male';
```
Filtering by Range - pets age from 2 to 5 years
```SQL
SELECT * FROM Pets WHERE age BETWEEN 2 and 5;
```
Filtering by Partial Match (LIKE) - Owners with ID starting with 13
```SQL
SELECT * FROM Pets WHERE OwnerID LIKE '13%';
```
Filtering by Multiple Conditions (AND) - birds of age of 3 years
```SQL
SELECT * FROM Pets WHERE Kind='Bird' AND age=3;
```
Filtering by Multiple Conditions (OR) - pets of age less than 2 years or birds
```SQL
SELECT * FROM Pets WHERE Kind='Bird' OR age<2;
```
Filtering by NULL Values - filters pets with non-defined age
```SQL
SELECT * FROM Pets WHERE age IS NULL;
```
Filtering by a Set of Values (IN) - filtering for birds and cats
```SQL
SELECT * FROM Pets WHERE Kind IN ('Bird', 'Cat');
```
Filtering by Condition with NOT - pets who are not birds
```SQL
SELECT * FROM Pets WHERE NOT Kind='Bird';
```
Filters names starting with 'C' and ending with 'y'
```SQL
SELECT * FROM Pets WHERE Name REGEXP '^C.y$'; .
```
Filters Age in descending order:
```SQL
SELECT FROM Pets ORDER BY Age DESC;
```
Filter names which starts with C and order by length of the Name:
```SQL
SELECT * FROM Pets WHERE Name LIKE 'C%' ORDER BY LENGTH(Name) ASC;
```
This query will return the first 50 rows from the Pets table, ordered by OwnerID in ascending order:
```SQL
SELECT * FROM Pets ORDER BY OwnerID ASC LIMIT 50;
```
Find all male pets older than 5 years:
```SQL
SELECT * FROM Pets WHERE Sex = 'male' AND Age > 5;
```
Sort pets by age in descending order:
```SQL
SELECT * FROM Pets ORDER BY Age DESC;
```
Sort pets by name alphabetically:
```SQL
SELECT * FROM Pets ORDER BY Name ASC;
```
Count the number of pets of each kind:
```SQL
SELECT Kind, COUNT(*) AS NumberOfPets FROM Pets GROUP BY Kind;
```
Find the average age of all pets:
```SQL
SELECT AVG(Age) AS AverageAge FROM Pets;
```
Find the average age of dogs:
```SQL
SELECT AVG(Age) AS AverageAge FROM Pets WHERE Kind = 'Dog';
```
Find pets with the same name:
```SQL
SELECT Name, COUNT(*) FROM Pets GROUP BY Name HAVING COUNT(*) > 1;
```
Find 5 the oldest female pets:
```SQL
SELECT * FROM Pets WHERE Sex = 'female' ORDER BY Age DESC LIMIT 1;
```
1. Filtering all pet names that are 10 characters long.
```SELECT name FROM Pets WHERE LENGTH(name) = 10;```

2. Filtering in "Pets" data dogs whose age is above 3 and whose name ends with "er"
```SELECT * FROM Pets WHERE Age > 3 AND NAME LIKE '%er';```

3. Filtering in all Pets Dogs with short names
```SELECT * FROM Pets WHERE LENGTH(Name) BETWEEN 2 AND 3 AND Kind = 'Dog';```

4. Filtering all female birds who are less than 3 years old
```SELECT * FROM Pets WHERE Kind = 'Bird' AND Sex = 'female' AND Age <= 3;```

5. Filtering all Pets with name "Simba"
```SELECT * FROM Pets WHERE Name IN ('Simba');```

```SQL
SELECT * FROM Pets WHERE Kind='Dog' AND Name GLOB '*An*';
SELECT * FROM Pets WHERE Kind='Dog' AND Name GLOB '*Vi*';
SELECT * FROM Pets WHERE Kind='Dog' AND Name GLOB '*Kir*';
SELECT * FROM Pets WHERE Kind='Dog' AND Name GLOB '*Han*';
SELECT * FROM pets WHERE kind= 'Cat' OR kind='Rabbit';
SELECT * FROM pets WHERE age BETWEEN 1 AND 5;
SELECT City, COUNT(*) AS OwnerCount FROM owners GROUP BY City ORDER BY OwnerCount DESC LIMIT 5;
SELECT Name, Age, Kind FROM Pets ORDER BY Age DESC LIMIT 1; -- the oldest Pet
SELECT Kind, Name, Age FROM Pets WHERE (Kind, Age) IN (SELECT Kind, MAX(Age) FROM Pets GROUP BY Kind); -- the oldest Pet of every Kind
SELECT Kind, COUNT(*) AS Count FROM Pets GROUP BY Kind; -- the no of Pets per Kind
SELECT Kind, AVG(Age) AS Average_Age FROM Pets GROUP BY Kind; -- Average age per Kind
SELECT p.Name AS PetName, p.Kind, o.Name AS OwnerName FROM Pets AS p JOIN Owners AS o ON p.OwnerID = o.OwnerID; -- Pets and Owners
SELECT OwnerID, COUNT(*) AS PetCount FROM Pets GROUP BY OwnerID HAVING COUNT(*) > 5; -- Owners with more than 5 Pets

SELECT Name FROM Pets WHERE Kind='Bird' 

SELECT * FROM Pets WHERE Kind='Bird' AND Sex='female';

SELECT * FROM Pets WHERE Kind='Cat' AND Name GLOB'si'; (NOT a lot Cats with si in name)

SELECT * FROM Pets WHERE Kind='Dog' AND Name GLOB'si'; (Dogs are more)

SELECT * FROM Pets WHERE Kind='Bird' AND Name GLOB'si'; (And only one bird)

SELECT * FROM Pets WHERE LENGTH(Name) BETWEEN 2 AND 5;

SELECT * FROM Pets WHERE Name BETWEEN 'A' AND 'D';

SELECT * FROM Pets WHERE Kind='Dog' AND Name BETWEEN 'A' AND 'D';

SELECT Name * FROM Pets ORDER BY Name ASC; (ordering names by alphabetically)

SELECT COUNT(*) FROM Pets; (Counting the number of pets in the table 2327)

SELECT AVG (Age) FROM Pets; (Calculates average age of all pets in the table witch is 11,22 years)

SELECT Kind, COUNT(*) AS NumberOfPets FROM Pets GROUP BY Kind; (This counts the number of pets for each kind Dogs 1231, Cats 863, Birds 233)

SELECT Name FROM Pets WHERE Name LIKE 'C%e'; (Give all pets names which start with C and ends with E like Cassie, Cookie)

SELECT name, COUNT(*) as name_count FROM pets GROUP BY name ORDER BY name_count DESC; (Gives most popular pet name, in our list is Biscuit most popular name)

SELECT Kind, COUNT(*) AS CountOfKind
FROM Pets
GROUP BY Kind;
```
--If there are multiple birds with the same maximum age, only one of them will be returned!
```SQL
SELECT *
FROM Pets
WHERE Kind = 'Bird'
ORDER BY Age DESC
LIMIT 1;
```
maximum number of pets owned by a single owner
```SQL
SELECT OwnerID, COUNT(*) AS NumberOfPets
FROM Pets
GROUP BY OwnerID
ORDER BY NumberOfPets DESC
LIMIT 1;
```
who are those pets exactly ?
```SQL
SELECT *
FROM Pets
WHERE OwnerID = (
    SELECT OwnerID
    FROM Pets
    GROUP BY OwnerID
    ORDER BY COUNT(*) DESC
    LIMIT 1
);
```

Male cat names that start with "S" who are aged less than 7 years:
```SQL
SELECT petid, name, ownerid FROM Pets WHERE kind='Cat' and name GLOB 'S' and age<7 and sex='male';
```
Pets that have letter "b" as third in their name :
```SQL
SELECT * FROM PETS WHERE name LIKE 'b';
```
Counting the number of pets each owner has:
```SQL
SELECT o.Name, COUNT(p.PetID) AS NumPets FROM Owners o LEFT JOIN Pets p ON o.OwnerID = p.OwnerID GROUP BY o.OwnerID;
```
Who has the most pets (It's Barbara):
```SQL
SELECT o.Name, COUNT(p.PetID) AS NumPets FROM Owners o LEFT JOIN Pets p ON o.OwnerID = p.OwnerID GROUP BY o.OwnerID ORDER BY NumPets DESC LIMIT 1;
```
Barbara owns all these pets:
```SQL
SELECT p.PetID, p.Name, p.Kind FROM Pets p WHERE p.OwnerID = ( SELECT o.OwnerID FROM Owners o LEFT JOIN Pets p ON o.OwnerID = p.OwnerID GROUP BY o.OwnerID ORDER BY COUNT(p.PetID) DESC LIMIT 1 );
```
Oldest pet and their owner:
```SQL
SELECT p.Name, p.Age AS PetAge, o.Name AS OwnerName FROM Pets p JOIN Owners o ON p.OwnerID = o.OwnerID ORDER BY p.Age DESC LIMIT 1;
```
The longest name:
```SQL
SELECT Name, LENGTH(Name) AS NameLength FROM Pets ORDER BY NameLength DESC LIMIT 1;
```
5 random pets:
```SQL
SELECT * FROM Pets ORDER BY RANDOM() LIMIT 5;
```
Who is the "Cat lady"? Turns out it's gentleman named Lionel and his five cats:
```SQL
SELECT o.OwnerID, o.Name, COUNT(p.PetID) AS NumCats FROM Owners o LEFT JOIN Pets p ON o.OwnerID = p.OwnerID WHERE p.Kind = 'Cat' GROUP BY o.OwnerID ORDER BY NumCats DESC LIMIT 1;
```
And Lionel's cats are:
```SQL
SELECT p.PetID, p.Name, p.Kind FROM Pets p WHERE p.OwnerID = ( SELECT o.OwnerID FROM Owners o LEFT JOIN Pets p ON o.OwnerID = p.OwnerID WHERE p.Kind = 'Cat' GROUP BY o.OwnerID ORDER BY COUNT(p.PetID) DESC LIMIT 1 ) AND p.Kind = 'Cat';
```
Average age of pets for each pet type:
```SQL
SELECT Kind, AVG(Age) AS AvgAge FROM Pets GROUP BY Kind;
```
Finds duplicates in names:
```SQL
SELECT Name, COUNT() FROM Pets GROUP BY Name HAVING COUNT() > 1;
```
Find all male pets older than 5 years:
```SQL
SELECT * FROM Pets WHERE Sex = 'male' AND Age > 5;
```
Sort pets by age in descending order:
```SQL
SELECT * FROM Pets ORDER BY Age DESC;
```
Sort pets by name alphabetically:
```SQL
SELECT * FROM Pets ORDER BY Name ASC;
```
Count the number of pets of each kind:
```SQL
SELECT Kind, COUNT(*) AS NumberOfPets FROM Pets GROUP BY Kind;
```
Find the average age of all pets:
```SQL
SELECT AVG(Age) AS AverageAge FROM Pets;
```
Find the average age of dogs:
```SQL
SELECT AVG(Age) AS AverageAge FROM Pets WHERE Kind = 'Dog';
```
Find pets with the same name:
```SQL
SELECT Name, COUNT(*) FROM Pets GROUP BY Name HAVING COUNT(*) > 1;
```
Find 5 the oldest female pets:
```SQL
SELECT * FROM Pets WHERE Sex = 'female' ORDER BY Age DESC LIMIT 1;
```
# Our group work
/* Average age of pets by Kind
SELECT Kind, AVG(Age) AS AverageAge
FROM Pets
GROUP BY Kind;*/

/* Exclude dogs and cats
SELECT * FROM Pets WHERE Kind != 'Dog' AND Kind != 'Cat';*/

/* Owner ID and which pets they own
SELECT OwnerID, GROUP_CONCAT(Name, ', ') AS Pets
FROM Pets
GROUP BY OwnerID;*/

/* Oldest pet by Age
SELECT Kind, Name, MAX(Age) AS OldestAge
FROM Pets
GROUP BY Kind;*/

/* Most common pet name
SELECT Name, COUNT(*) AS Frequency
FROM Pets
GROUP BY Name
ORDER BY Frequency DESC
LIMIT 5;*/

/* All pets owned by owners from the same city "Livonia"
SELECT Pets.Name AS PetName, Owners.Name AS OwnerName, Owners.City 
FROM Pets 
JOIN Owners ON Pets.OwnerID = Owners.OwnerID 
WHERE Owners.City = 'Livonia';*/

/* Owner name and pet name the same
SELECT p.PetID, p.Name AS PetName, p.Kind, p.Sex, p.Age, o.Name AS OwnerName
FROM Pets p
JOIN Owners o ON p.OwnerID = o.OwnerID
WHERE p.Name = o.Name;*/

/* All the owners of pet name Bruce
SELECT Pets.Name AS PetName, Owners.Name AS OwnerName
FROM Pets
JOIN Owners ON Pets.OwnerID = Owners.OwnerID
WHERE Pets.Name='Bruce'*/

/* Owner names and pet names they own
SELECT Owners.Name AS HumanName, Pets.Name AS PetName
FROM Owners
JOIN Pets ON Owners.OwnerID = Pets.OwnerID
GROUP BY Owners.Name, Pets.Name;*/

/* Owners name and surname who havs at least 2 pets, in an alphabetical order
SELECT 
    p1.Name AS Pet1_Name,
    p2.Name AS Pet2_Name,
    o.Name AS Owner_First_Name,
    o.Surname AS Owner_Last_Name
FROM 
    Pets p1
    INNER JOIN Pets p2 ON p1.OwnerID = p2.OwnerID AND p1.PetID < p2.PetID
    INNER JOIN Owners o ON p1.OwnerID = o.OwnerID
ORDER BY 
    o.Name,
   o.Surname, 
    p1.Name, 
    p2.Name;*/
    
    
/* All pets owned by owners with more than 1 pet, ordered by owner's first name alphabetically
SELECT 
    p.Name AS Pet_Name,
    p.Kind,
    p.Sex AS Pet_Sex,
    p.Age AS Pet_Age,
    o.Name AS Owner_First_Name,
    o.Surname AS Owner_Last_Name
FROM 
    Pets p
    INNER JOIN Owners o ON p.OwnerID = o.OwnerID
WHERE 
    p.OwnerID IN (
        SELECT OwnerID
        FROM Pets
        GROUP BY OwnerID
        HAVING COUNT(PetID) > 1
    )
ORDER BY 
    o.Name;*/

/* Pets with name length <3
SELECT *
FROM Pets
WHERE LENGTH(Name) < 3;*/

/* All female pets from Detroit 
SELECT Pets.Name, Owners.City 
FROM Pets 
JOIN Owners ON Pets.OwnerID = Owners.OwnerID 
WHERE Pets.Sex = 'female' AND Owners.City = 'Detroit';*/

# Second Lesson

![image](https://github.com/user-attachments/assets/30a7c3c0-a532-4f32-bf7d-8e47e5951bbd)


SELECT Pets.*, Owners.*
FROM Pets LEFT JOIN Owners ON Pets.OwnerID = Owners.OwnerID;

SELECT Pets.*, Owners.City
FROM Pets LEFT JOIN Owners ON Pets.OwnerID = Owners.OwnerID;

SELECT Pets.Name AS PetName, Owners.Name AS OwnerName, Owners.City 
FROM Pets 
JOIN Owners ON Pets.OwnerID = Owners.OwnerID 
WHERE Owners.City = 'Flint';

SELECT Pets.Kind, COUNT(*) AS count
FROM Pets
GROUP BY Kind;
FROM Pets LEFT JOIN Owners 
ON Pets.OwnerID = Owners.OwnerID 
WHERE Owners.City = 'Flint';

SELECT Kind, COUNT(*) AS Count 
FROM Pets 
GROUP BY Kind
ORDER BY Count DESC;
SELECT Pets.*, Owners.City
FROM Pets LEFT JOIN Owners ON Pets.OwnerID = Owners.OwnerID;

SELECT Owners.City, COUNT(*) AS PetCount
FROM Pets
JOIN Owners ON Pets.OwnerID = Owners.OwnerID
GROUP BY Owners.City
ORDER BY PetCount Desc;

### For every city all three pet kinds are counted
```SQL
SELECT Owners.City, Pets.Kind, 
COUNT(*) AS PetCount
FROM Pets
JOIN Owners ON Pets.OwnerID = Owners.OwnerID
GROUP BY Owners.City, Pets.kind;

SELECT Pets.Name
FROM Pets
LEFT JOIN Owners ON Pets.OwnerID = Owners.OwnerID
WHERE Owners.OwnerID IS NULL;

SELECT Procedures.ProcedureType, SUM(Procedures.Price) AS TotalSales
FROM Sales
JOIN Procedures 
ON Sales.ProcedureCode = Procedures.ProcedureCode
GROUP BY Procedures.ProcedureType;
```

# Teamwork
### Calculate total Sales by City
```SQL
SELECT Owners.City, SUM(Procedures.Price) AS TotalSales
FROM Sales 
JOIN Procedures ON Sales.ProcedureCode = Procedures.ProcedureCode 
JOIN Owners ON Pets.OwnerID = Owners.OwnerID
JOIN Pets ON Pets.PetID = Sales.PetID
GROUP BY Owners.City
ORDER BY TotalSales DESC;
```
### Calculate total Sales by Pet Kind
```SQL
SELECT Pets.Kind, SUM(Procedures.Price) AS TotalSales
FROM Sales
LEFT JOIN Procedures ON Sales.ProcedureCode = Procedures.ProcedureCode
LEFT JOIN Pets ON Sales.PetID = Pets.PetID
GROUP BY Pets.Kind
ORDER BY TotalSales DESC;
```

### Calculate total Sales by City and Pet Kind
```SQL
SELECT Owners.City, Pets.Kind, SUM(Procedures.Price) AS TotalSales
FROM Sales 
JOIN Procedures ON Sales.ProcedureCode = Procedures.ProcedureCode 
JOIN Owners ON Pets.OwnerID = Owners.OwnerID
JOIN Pets ON Pets.PetID = Sales.PetID
GROUP BY Owners.City, Pets.Kind;
```

### Calculate Average sales by City
```SQL
SELECT Owners.City, AVG(Procedures.Price) AS TotalSales
FROM Sales 
JOIN Procedures ON Sales.ProcedureCode = Procedures.ProcedureCode 
JOIN Owners ON Pets.OwnerID = Owners.OwnerID
JOIN Pets ON Pets.PetID = Sales.PetID
GROUP BY Owners.City
ORDER BY TotalSales DESC;
```

### If you have additional time, explore relationships with SQLight - ChatGPT to a 5yo
Imagine you have two toy boxes. One box has a bunch of cars, and the other box has a bunch of drivers. Each car has a driver, and each driver has a car they drive.

Now, what if you wanted to know which driver drives which car? You could put a sticker on each car with the driver's name. This way, whenever you pick up a car, you know exactly who drives it.

In SQLite (which is like a big toy box for computers), a relationship is like the sticker that tells the computer which things (like cars and drivers) go together.

