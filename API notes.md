# API Application Programming Interface
Access point where 2 programs are interacting with each other

Client --> sending data --> API Controller (server) --> Service (Business logic, actual requirements) - Checks rules and validation, give reply; processes, analyzes
--> Data, Repo (DB services; is the user real? Data layer gives an aswer) --> queries --> DB

JAVA --> translator, commmunicator, repo, driver --> Database (DB) (can be in different languages)

JAVA --> ORM, Hibernate, Java-Framework --> (or via Dialect and Driver) --> DB

Create controller that connects to everything. 
Create controller --> DTO --> Service --> DTO --> Repo (Chain reaction)

Repo goes back and forth to/from DB, same functions as controller. 

User Service has its own spoon (userRepo), and we don't want to share spoons. 

User Controller

User Service
new UserService - userService = new UserService
UserRepo
new UserRepo - userRepo = new UserRepo
DB

or Singleton in Main. 

get UserController --> Service --> Repo
return all users in the ArrayList users

### Setting up API
sqlite - jdbc: 3.46.1.3
orm: hibernate-core: 6.6.1.Final
orm: hibernate-community-dialects: 6.3.1.Final

ORM (Hibernate) - object-relational-mapping - layer between repo and DB
data from DB --> ORM --> DTOs & entities (java object)

Hibernate library - creating a DB
Factory creates and saves an object that connects to DB. 
DTO belongs to the Repo

### Business logic - authentication logic
On Government page we can use different banks to log in, however we have no control over what's going on on the bank's side. 
Interface defines the rules of authentication service. Interface is abstract class with empty body. Choose to use multiple interfaces. 

### Unit test
Name of the unit-test: describe what happens - When_Then

Testing Service wothout Repo so tests wouldn't affect the actual DB. 
Repos are rarely tested. 

TDD - test driven development - writing unit-test to break the current method

### Mock test 
makes unit test repeatable
simulates external dependencies
helps simulate thebehaviour of external systems
tests code in isolation
verifies interactions
controls return values
increases test reliability

Mocking helps to isolate the unit you're testing; control over behavour, speed & simplicity, verify interactions. 

The random that is the power of nano-time

C# Microsoft ~ Visual Studio, Azure, MS SQL, .Net ~ Java

C++  ~ C

Java --> JSON - SpringBoot

### Databases

Repository --> Driver = translator; 1 connection, 1 query --> DB (Oracle, My SQL, SQLite etc) (limit of e-g- 5 connections, if more it will be rejected)
           <--             Get response                   <--

1. Start connection
2. Use connection - update / delete / add data
3. End connection

User.Repo.java
public void add(User user)
String url =
try
  if
  var statement
  }
  } catch (SQLExeption e)

dependencies
build.gradle

User repo --> SQL
user.name
xerial sqlite jdbc

jdbc:quarkus-jdbc 3.07

data structure SET
List where every object is unique but you can't access a specific object.
Going from one element to the next while the last element is destroyed. 


## Postman
### controller 
@Postmapping ("/add")
public int add (@RequestBody User user){
  return: userService.add(user);}

### service
public int add (User user({
  return userRepo.add(user);}

### repo
public ArrayList <User> get(){ #getting users from private property
  return users;}

public User get (int id){
return users-get (id);
  
public int add (User user){
  users.add (user);
    return users.size();}

* one "get" in repo --> divide into details in service
* DTP (data transfer object) - for communication through layers --> in Potman Body row JSON {"user index" = 1, "user": { "name" : "Oskars"}}
* Entity is an object in DB

Update username / POST method - does this username exist?
Update birthyear / POST method - does this user exist?
Get profile / GET method - does this user exist?

DB - Devices - Web - UI - External Interfaces
Controllers
Use Cases
Entities, DTOs

### Clean Architecture
Freakonomics

### Protocols
Services communicate with each other through protocols
Card payment - NFC protocol
bluetooth - some protocol
Front end --> <-- Back end - HTTP protocol (hypertext transfer protocol)

Header
Body - parameter (Oskars)
Payload

### Errors
4040 - page not found
200 - good
400 - bad
500 - error in server

### Attribute / annotation @GetMapping
adds properties to the function "/ping"
doesn't impact how the function runs

%s placeholder for a string - java string interpolation

API
Requests Responses
Spring
    



