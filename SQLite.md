# SQLite

# First lesson - FILTERING
Find all pets that are older than 5 years:
SELECT FROM Pets WHERE Age > 5;
Find all owners living in a specific city:
SELECT * FROM Owners WHERE City = 'Detroit';
Find all procedures that cost more than $100:
SELECT * FROM Procedures WHERE Price > 100;
Multiple Filters
Find male pets that are older than 3 years:
SELECT FROM Pets WHERE Sex = 'male' AND Age > 3;
Find owners who live in a particular state and city:
SELECT * FROM Owners WHERE State = 'MI' AND City = 'Livonia';
Find procedures with a specific type and price range:
SELECT * FROM Procedures WHERE ProcedureType = ' ORTHOPEDIC' AND Price BETWEEN 200 AND 500;
*Using JOINs and Filters
Find all pets along with their owners' details:
SELECT Pets.Name, Pets.Kind, Owners.Name, Owners.Surname
FROM Pets
JOIN Owners ON Pets.OwnerID = Owners.OwnerID;
Find owners who have pets of a particular kind (e.g., dogs):
SELECT Owners.Name, Owners.Surname
FROM Owners
JOIN Pets ON Owners.OwnerID = Pets.OwnerID
WHERE Pets.Kind = 'Dog';
Combining Filters with Aggregates
Find the average age of all pets in the database:
SELECT AVG(Age) AS AverageAge FROM Pets;
Find the number of procedures that cost more than $150:
SELECT COUNT() AS ExpensiveProcedures FROM Procedures WHERE Price > 150; Using LIKE for Pattern Matching
Find all owners whose surname starts with 'S':
SELECT FROM Owners WHERE Surname LIKE 'S%';

Find all pets with names that end in 'y':
SELECT * FROM Pets WHERE Name LIKE '%y';
Using IN and NOT IN
Find all pets that are not dogs or cats:
SELECT FROM Pets WHERE Kind NOT IN ('Dog', 'Cat');
Using BETWEEN and Date Filters
Find all procedures performed between two dates:
SELECT FROM Sales WHERE Date BETWEEN '06/03/2018' AND '26/05/2019';
Find all pets that are between 2 and 8 years old:
SELECT * FROM Pets WHERE Age BETWEEN 2 AND 8; 

SELECT * FROM Pets WHERE LENGTH(Name) = 5;
SELECT * FROM Pets WHERE Name LIKE '%er';
SELECT DISTINCT Kind FROM Pets;

How many diferent type of pets there are?
SELECT kind, COUNT(*) AS Count 
FROM Pets 
GROUP BY Kind
ORDER BY Count DESC;

What is the most popular pet name? 
SELECT Name, COUNT(*) AS Count 
FROM Pets 
GROUP BY Name
ORDER BY Count DESC;

What is most common pet age?

SELECT Age, COUNT(*) AS Count
FROM Pets
GROUP BY Age
ORDER BY Count DESC
LIMIT 1;

What are the top 3 longest pet names?
SELECT *
FROM Pets 
ORDER BY LENGTH(Name) DESC
LIMIT 3;
 
What is the biggest number of pets an owner has? 
SELECT OwnerID, COUNT(*) AS PetCount
FROM Pets
GROUP BY OwnerID
ORDER BY PetCount DESC
LIMIT 1;

What is the avarage age of the previous owners pets? 
SELECT AVG(Age) AS AverageAge
FROM Pets
WHERE OwnerID = 4782;

# Second Lesson

SELECT Pets.*, Owners.*
FROM Pets LEFT JOIN Owners ON Pets.OwnerID = Owners.OwnerID;

SELECT Pets.*, Owners.City
FROM Pets LEFT JOIN Owners ON Pets.OwnerID = Owners.OwnerID;

SELECT Pets.Name AS PetName, Owners.Name AS OwnerName, Owners.City 
FROM Pets 
JOIN Owners ON Pets.OwnerID = Owners.OwnerID 
WHERE Owners.City = 'Flint';

SELECT Pets.*, Owners.City 
FROM Pets LEFT JOIN Owners 
ON Pets.OwnerID = Owners.OwnerID 
WHERE Owners.City = 'Flint';

SELECT Pets.*, Owners.City
FROM Pets LEFT JOIN Owners ON Pets.OwnerID = Owners.OwnerID;
