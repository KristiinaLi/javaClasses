## Main.java
```java
import java.util.InputMismatchException;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        CheeseService cheeseService = new CheeseService();
        Customer customer = new Customer("John Doe", 100);
        CheeseShop cheeseShop = new CheeseShop(cheeseService, customer);

        Scanner scanner = new Scanner(System.in);

        while (true) {
            System.out.println("Do you want to enter Cheese Service or Cheese Shop?");
            System.out.println("    Type 'service' for Cheese Service.");
            System.out.println("    Type 'shop' for Cheese Shop.");
            System.out.println("    Type 'exit' to quit.");

            String answer = scanner.nextLine().strip().toLowerCase();

            switch (answer) {
                case "service":
                    handleCheeseService(scanner, cheeseService);
                    break;
                case "shop":
                    handleCheeseShop(scanner, cheeseShop);
                    break;
                case "exit":
                    System.out.println("Exiting the program. Goodbye!");
                    return;
                default:
                    System.out.println("Invalid input! Please enter 'service', 'shop' or 'exit'.");
            }
        }
    }

    private static void handleCheeseService(Scanner scanner, CheeseService cheeseService) {
        while (true) {
            System.out.println("Welcome to Cheese Service! What would you like to do?");
            System.out.println("Press 1 to Add Cheese");
            System.out.println("Press 2 to Remove Cheese");
            System.out.println("Press 3 to Display Cheese Inventory");
            System.out.println("Press 4 to Exit");

            int serviceAction = getIntInput(scanner);
            if (serviceAction == -1) continue;

            switch (serviceAction) {
                case 1:
                    System.out.println("Enter cheese name: ");
                    String cheeseName = scanner.nextLine();
                    System.out.println("Enter cheese price: ");
                    float price = getFloatInput(scanner);
                    if (price == -1) continue;
                    System.out.println("Enter quantity: ");
                    int quantity = getIntInput(scanner);
                    if (quantity == -1) continue;
                    cheeseService.addStock(cheeseName, price, quantity);
                    break;
                case 2:
                    System.out.println("Enter cheese name: ");
                    cheeseName = scanner.nextLine();
                    System.out.println("Enter quantity to remove: ");
                    quantity = getIntInput(scanner);
                    if (quantity == -1) continue;
                    cheeseService.removeStock(cheeseName, quantity);
                    break;
                case 3:
                    System.out.println("Cheese Inventory:");
                    for (Cheese cheese : cheeseService.getCheeses()) {
                        System.out.println(cheese.getCheeseName() + ": " + cheese.getQuantity() + " units at €" + cheese.getPrice() + " each");
                    }
                    break;
                case 4:
                    System.out.println("Exiting Cheese Service.");
                    return;
                default:
                    System.out.println("Invalid action! Please enter a number between 1 and 4.");
            }
        }
    }

    private static void handleCheeseShop(Scanner scanner, CheeseShop cheeseShop) {
        while (true) {
            System.out.println("Welcome to Cheese Shop!");
            System.out.println("Press 1 to See cheeses available.");
            System.out.println("Press 2 to Add cheese to cart.");
            System.out.println("Press 3 to Remove cheese from cart.");
            System.out.println("Press 4 to See the checkout.");
            System.out.println("Press 5 to Buy the cart.");
            System.out.println("Press 6 to Exit");

            int shopAction = getIntInput(scanner);
            if (shopAction == -1) continue;

            switch (shopAction) {
                case 1:
                    System.out.println("Available cheeses:");
                    for (Cheese cheese : cheeseShop.listAllCheeses()) {
                        System.out.println(cheese.getCheeseName() + ": " + cheese.getQuantity() + " units at €" + cheese.getPrice() + " each");
                    }
                    break;
                case 2:
                    System.out.println("Enter cheese name:");
                    String cheeseName = scanner.nextLine();
                    System.out.println("Enter quantity:");
                    int quantity = getIntInput(scanner);
                    if (quantity == -1) continue;
                    cheeseShop.addToCart(cheeseName, quantity);
                    break;
                case 3:
                    System.out.println("Enter cheese name:");
                    cheeseName = scanner.nextLine();
                    System.out.println("Enter quantity to remove:");
                    quantity = getIntInput(scanner);
                    if (quantity == -1) continue;
                    cheeseShop.removeFromCart(cheeseName, quantity);
                    break;
                case 4:
                    System.out.println("Total price of items in cart: €" + cheeseShop.displayCart());
                    break;
                case 5:
                    cheeseShop.buyCart();
                    break;
                case 6:
                    System.out.println("Exiting Cheese Shop.");
                    return;
                default:
                    System.out.println("Invalid action! Please enter a number between 1 and 6.");
            }
        }
    }

    private static int getIntInput(Scanner scanner) {
        int input = -1;
        try {
            input = scanner.nextInt();
            scanner.nextLine();
        } catch (InputMismatchException e) {
            System.out.println("Invalid input! Please enter a valid number.");
            scanner.nextLine();
        }
        return input;
    }

    private static float getFloatInput(Scanner scanner) {
        float input = -1;
        try {
            input = scanner.nextFloat();
            scanner.nextLine();
        } catch (InputMismatchException e) {
            System.out.println("Invalid input! Please enter a valid number.");
            scanner.nextLine();
        }
        return input;
    }
}
```

## Cheese.java
```java
import java.util.ArrayList;

public class Cheese {
    private String cheeseName;
    private float price;
    private int quantity;

    public Cheese(String cheeseName, float price, int quantity) {
        this.cheeseName = cheeseName;
        this.price = price;
        this.quantity = quantity;
    }

    public String getCheeseName() {
        return cheeseName;
    }

    public void setCheeseName(String cheeseName) {
        this.cheeseName = cheeseName;
    }

    public float getPrice() {
        return price;
    }

    public void setPrice(int price) {
        this.price = price;
    }

    public int getQuantity() {
        return quantity;
    }

    public void setQuantity(int quantity) {
        this.quantity = quantity;
    }
}
```

## Customer.java
```java
import java.util.HashMap;
import java.util.Map;

public class Customer {
    private String customerName;
    private float balance;
    private static Map<String, Customer> customers = new HashMap<>();

    public Customer (String customerName, float balance) {
        this.customerName = customerName;
        this.balance = balance;
    }

    public String getCustomerName() {
        return customerName;
    }

    public void setCustomerName(String customerName) {
        this.customerName = customerName;
    }

    public float getBalance() {
        return balance;
    }

    public void setBalance(float balance) {
        this.balance = balance;
    }

    public static void addCustomer(Customer customer) {
        customers.put(customer.getCustomerName(), customer);
    }
    public static void removeCustomer(String customerName) {
        customers.remove(customerName);
    }
    public static Customer getCustomer(String customerName) {
        return customers.get(customerName);
    }
    public boolean customerExists(String customerName) {
        return customers.containsKey(customerName);
    }
}
```

## CheeseService.java
```java
import java.util.ArrayList;
import java.util.List;

public class CheeseService {
    private List<Cheese> cheeses = new ArrayList<>();

    public List<Cheese> getCheeses() {
        return new ArrayList<> (cheeses);
    }

    public void addStock(String cheeseName, float price, int quantity) {
        for (Cheese cheese : cheeses) {
            if (cheese.getCheeseName().equals(cheeseName)) {
                cheese.setQuantity(cheese.getQuantity() + quantity);
                return;
            }
        }
        cheeses.add(new Cheese(cheeseName, price, quantity));
    }
    public void removeStock(String cheeseName, int quantity) {
        for (Cheese cheese : cheeses) {
            if (cheese.getCheeseName().equals(cheeseName)) {
                int currentQuantity = cheese.getQuantity();
                if (currentQuantity <= quantity) {
                    cheeses.remove(cheese);
                } else {
                    cheese.setQuantity(currentQuantity - quantity);
                }
                return;
            }
        }
    }
}
```

## CheeseShop.java
```java
import java.util.ArrayList;
import java.util.List;

public class CheeseShop {
    private CheeseService cheeseService;
    private Customer customer;
    private List<Cheese> cart = new ArrayList<>();

    public CheeseShop(CheeseService cheeseService, Customer customer) {
        this.cheeseService = cheeseService;
        this.customer = customer;
    }

    public List<Cheese> listAllCheeses() {
        return cheeseService.getCheeses();
    }

    public void addToCart(String cheeseName, int quantity) {
        Cheese cheeseInStock = null;
        for (Cheese c : cheeseService.getCheeses()) {
            if (c.getCheeseName().equals(cheeseName)) {
                cheeseInStock = c;
                cart.add(cheeseInStock);
                break;
            }
        }
        if (cheeseInStock != null) {
            for (int i = 0; i < quantity; i++) {
                cart.add(new Cheese(cheeseInStock.getCheeseName(), cheeseInStock.getPrice(), 1));
            }
            System.out.println(quantity + " " + cheeseName + " added to the cart");
        } else {
            System.out.println(cheeseName + " not available in stock.");
        }
    }

    public void removeFromCart(String cheeseName, int quantity) {
        int removedCount = 0;
        for (int i = 0; i < cart.size() && removedCount < quantity; i++) {
            if (cart.get(i).getCheeseName().equals(cheeseName)) {
                cart.remove(i);
                i--;
                removedCount++;
            }
        }
        if (removedCount > 0) {
            System.out.println(removedCount + " " + cheeseName + " removed from the cart");
        } else {
            System.out.println(cheeseName + " is not in the cart.");
        }
    }

    public float displayCart() {
        for (Cheese cheese : cart) {
            System.out.println("You're cart contains " + cheese.getCheeseName() + " " + cheese.getPrice());
        }
        float priceTotal = 0;
        for (Cheese cheese : cart) {
            priceTotal += cheese.getPrice();
        }
        return priceTotal;
    }

    public void buyCart() {
        float totalCost = displayCart();
        if (customer.getBalance() >= totalCost) {
            customer.setBalance(customer.getBalance() - totalCost);
            cart.clear();
            System.out.println("Purchase successful. Remaining balance: " + customer.getBalance());
        } else {
            System.out.println("Insufficient balance to complete the purchase.");
        }
    }
}
```
