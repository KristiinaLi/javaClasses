# Cheese
name
how many
price

# Customer
Name - username, password
Balance
Basket

# Shop
Buy Cheese - add to cart, remove from cart, finish shopping (buy cheese in the cart)

# Cheese Service
Login - username, password
Check availability - CheeseForSaleList [name, quantity]; 
Add/remove cheese - AddCheese [name, quantity] = [key:value pairs]; RemoveCheese - Reduce the nr of cheese by name;

# Main
User UI
Access CheeseService, CheeseShop to add cheese, buy cheese

import Java.util.Scanner

What would you like to do today?
Press 1 to enter as customer
Press 2 to enter as shop owner
Press 3 to quit

As Owner
Press 1 check availability (see the list)
Press 2 to add cheese
Press 3 to remove cheese

As Client
Press 1 to see the CheeseForSale - check availability, see the list
Press 2 to AddToCart by name
Press 3 to RemoveFromCart by name
Press 4 to See the cart and cost - add up the cost of different cheeses
Press 5 to Buy the cheese in cart; If not enough balance, decline the deal
Press 6 to quit



Pre
