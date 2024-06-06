## To do list

Example of how it can be defined (public class Task --> public String name = "skjhegi"; or we can also just leave it be public String name;
```java
public class Task{
  //name, description, isDone
  public String name = "akjhsd";
  public String description = "value";
  public boolean isDone = "false"; // boolean is by default false

  // var task = new Task(name, description);
  public Task(String name, String description){
    this.name = name;
    this.description = decription;
  }
}
```

# To-do-list code
## Main
// Simple to-do application
/* 3 classes
1. main.java --> getting user input, sending input to taskManager, show information to the user
2. task.java -> task name, date, id, status (template for a task)
3. taskManager.java -> add, mark as done, get list; uses task.java


  */
import java.util.Scanner;
/* The main should be the only place we use static, Scanner and System.out.println because users only work with user interfaces, and the main represents UI for us (front end).
  */

```java
public class Main {

  public static TaskManager taskManager = new TaskManager();
  // outside of main class
  
  public static void main(String[] args) {
    createTask();
    showToDoList();
    // Use scanner, 
    // if the user presses 1, we call createTask
    // if the user presses 2, we call showToDoList
    // if the user presses 3, we mark a task as done (=true)
    // put it in a while loop
    // if the user presses x, close the loop
  }

  public static void createTask(){
    Scanner scanner = new Scanner(System.in);
  //While loop
    while(scanner != "x"){                                         // need to fix this
    System.out.println("Choose what you would like to do:");
    System.out.println("  Press 1 to create a task");
    System.out.println("  Press 2 to see to-do list");
    System.out.println("  Press 3 to mark a task as done");
    System.out.println("  Press x to exit");
  }
    
    System.out.println("Please input the name of the task: ");
    var name = scanner.nextLine();
    
    System.out.println("Please input the description of the task: ");
    var description = scanner.nextLine();
    scanner.close(); // because we create multiple scanners, we need to close them.
    var task = new Task(name, description);
    taskManager.addTask(task);
  }
  public static void showToDoList (){
    var tasks = taskManager.getTasks();
    for(var task : tasks){
      System.out.println("This is a task: ");
      System.out.println(task.name);
      System.out.println(task.description);
      System.out.println(task.isDone);
    }
  }
}
```

## Task
```java
public class Task{
  //name, description, isDone
  public String name;
  public String description;
  public boolean isDone; // boolean is by default false

  // var task = new Task(name, description);
  public Task(String name, String description){
    this.name = name;
    this.description = description;
  }
}
```
## TaskManager
```java
import java.util.ArrayList;
  
public class TaskManager{
  // MVP: minimum viable product
  // Be able to add a Task -> DONE
  // Have a list of all the tasks -> getTasks();
  // Mark a task as done by Task name

  private ArrayList<Task> tasks = new ArrayList<Task>(); // private so that only taskManager can access it, no other classes can touch it (overwrite enything), but it provides values. Encapsulation. 

  // Because we want to use the default constructor
  // new TaskManager() - we don't need to add a custom constructor

  //Adding a task to taskManager, but we don't need to get anything back.
  // it exists so that it can access task ArrayList, we don't want to do anything else here.
  public void addTask(Task task){ // task object added
    tasks.add(task);    
  }

  // create a getter; provide a value to the user
  // this ensures tha the user can't change the value of the task.
  public ArrayList<Task> getTasks(){
    return tasks;
  }

  // public void removeTask(String name){
    // find task from name and remove it
  }
  
  // BONUS:
   // Get a random quote to stop procrastination
  // a list of done tasks - filter
  // a list of undone tasks - filter
}
```

## Almost final code

### Main.java (Is the UI - frontend)
```java
import java.util.Scanner;

public class Main { 

    public static TaskManager taskManager = new TaskManager();

    public static void main(String[] args) {
        
      while(true){
        Scanner scanner = new Scanner(System.in);
        System.out.println("Choose what you would like to do:");
        System.out.println("  Press 1 to create a task");
        System.out.println("  Press 2 to see to-do list");
        System.out.println("  Press 3 to mark a task as done");
        System.out.println("  Press x to exit");

        var userInput = scanner.nextLine();
        if(userInput.equals("1")){
          createTask();
        }else if(userInput.equals("2")){
          showTodoList();
        }else if(userInput.equals("3")){
          System.out.println("Enter the finished task name:");
          var taskName = scanner.nextLine();
          taskManager.setTaskAsDone(taskName);
        }else{
          break;
        }
        }
    }

    public static void createTask(){
        Scanner scanner = new Scanner(System.in);
        // Input the task name
        System.out.println("Please input the name of the task");
        var name = scanner.nextLine();
        // Input the task description
        System.out.println("Please input the description of the task");
        var description = scanner.nextLine();
        
        var task = new Task(name, description);
        taskManager.addTask(task);
    }

    public static void showTodoList(){
        var tasks = taskManager.getTasks();
        for(var task : tasks){
            System.out.println("Here are your TASKs");
            System.out.println("  " + task.name);
            System.out.println("  " + task.description);
            System.out.println("  " + task.isDone);
        }
    }
}
```

## TaskManager.java
```java
import java.util.ArrayList;

public class TaskManager{
  //MVP: Minimum Viable Product
  //Be able to add a Task -> DONE
  //Have a list of all the tasks -> getTasks();
  //Set a task as done, by Task name

  private ArrayList<Task> tasks = new ArrayList<Task>();

  //Because we want to use the default construcor
  // new TaskManager() - we don't need to add a custom constructor

  public void addTask(Task task){
    tasks.add(task);
  }

  public ArrayList<Task> getTasks(){
    return tasks;
  }

  public void setTaskAsDone(String taskName){
    tasks.stream()
      .filter(x -> x.name.equals(taskName))
      .findFirst()
      .ifPresent(x -> x.isDone = true);
  }

  //BONUS:
  //Get a random quote to stop procrastinating
  //A list of undone tasks - filter
  //A list of done tasks - filter
}
```

## Task.java
```java
public class Task{
  public String name;
  public String description;
  public boolean isDone;

  // var task = new Task(name, description);
  public Task(String name, String description){
    this.name = name;
    this.description = description;
  }
}
```

# Extra getters-and-setters

## Main.java
```java
public class Main {
  public static void main(String[] args) {
    var item = new Item();
    item.setName("This is a name");
    var itemName = item.getName();
  }

}
```

## Item.java
```java
public class Item{
  private String name; // if public, we could use item.name = "another name"; in the main method. But we don't want to do that. So we set it as private.
  private int cost; // Gold pieces

  /*
  Getters and setters are useful when you want to make sure that the data is not being changed by accident. They operate on the private variables on the back end.
  */

  public void setName(String name) {
    // Do some logic here e.g. username changed etc
    this.name = name;
    // Do some logic here
  }
  public String getName() {
    return name;
  }
  public void setCost(int cost) {
    this.cost = cost;
  }
  public int getCost() {
    return cost;
  }
}
```

# Final to-do-list
## Main.java
```java
import java.util.Scanner;

public class Main { //Is the UI - frontend

    public static TaskManager taskManager = new TaskManager();

    public static void main(String[] args) {
        actionPlan(); 
    }

    public static void createTask(){
        Scanner scanner = new Scanner(System.in);
        // Input the task name
        System.out.println("Please input the name of the task");
        var name = scanner.nextLine();
        // Input the task description
        System.out.println("Please input the description of the task");
        var description = scanner.nextLine();
        
        var task = new Task(name, description);
        taskManager.addTask(task);
    }

    public static void showTodoList(){
        var tasks = taskManager.getTasks();
        System.out.println("Here are your Tasks");
        for(var task : tasks){
            System.out.println("  " + task.name);
            // System.out.println("  " + task.description);
            System.out.println("  " + task.isDone);
        }
    }
    public static void actionPlan(){
      while(true){
        Scanner scanner = new Scanner(System.in);
        System.out.println("Choose what you would like to do:");
        System.out.println("  Press 1 to Create a task");
        System.out.println("  Press 2 to See to-do-list");
        System.out.println("  Press 3 to Mark a task as done");
        System.out.println("  Press x to Exit");

        var userInput = scanner.nextLine();
        if(userInput.equals("x")){
          System.out.println("Done for today. Bye!");
          break;
        }
        if(userInput.equals("1")){
          createTask();
        }else if(userInput.equals("2")){
          showTodoList();
        }else if(userInput.equals("3")){
          System.out.println("Enter the finished task name:");
          var taskName = scanner.nextLine();
          taskManager.setTaskAsDone(taskName);
        }else{
          System.out.println("Invalid input. Please try again.");
        }
    }
  }
}
```

## Task.java
```java
public class Task{
  public String name;
  public String description;
  public boolean isDone;

  // var task = new Task(name, description);
  public Task(String name, String description){
    this.name = name;
    this.description = description;
  }
}
```

## TaskManager.java
```java
import java.util.ArrayList;

public class TaskManager{
  //MVP: Minimum Viable Product
  //Be able to add a Task -> DONE
  //Have a list of all the tasks -> getTasks();
  //Set a task as done, by Task name

  private ArrayList<Task> tasks = new ArrayList<Task>();

  //Because we want to use the default construcor
  // new TaskManager() - we don't need to add a custom constructor

  public void addTask(Task task){
    tasks.add(task);
  }

  public ArrayList<Task> getTasks(){
    return tasks;
  }

  public void setTaskAsDone(String taskName){
    tasks.stream()
      .filter(x -> x.name.equals(taskName))
      .findFirst()
      .ifPresent(x -> x.isDone = true);
  }

  //BONUS:
  //Get a random quote to stop procrastinating
  //A list of undone tasks - filter
  //A list of done tasks - filter
}
```
