## How to go about solving the exercises
State the facts you already know, and then build up from there. 
What do I already know?
What can I base my conditions on?


## 1 Where is our result in the array?

How to solve this exercise?
Let's say it's a throwing competition, and the current results are 50m, 47m, and 44m. 
We throw 46, and now we want to know where we are placed with our result. 

// int [] results = {50, 47, 44}; our result = 46
// 1st place is biggest number and index 0
// 2nd place is second biggest number and index 1
// 3rd place is smallest number and index 2
// Figure out the correct place in the array
// Find the first number that is smaller than our number. 
// Add 46 to the array, find out the index of the number
// Place = i + 1

/* [8, 7, 5, 3, 2, 1]
Where does 4 go to?

1. Go through the array - for loop
2. Find a number less than our number - if
  3. Increment index by 1
  4. Return index
5. If we can't find a number smaller than our number
6. Return total count + 1.
  */
   
´´´java
public class Main {
    public static void main(String[] args) {
        int[] arr = {8, 7, 5, 3, 2, 1}; // current race results
        int number = 4; // our result
        boolean thePlaceIsFound = false;
        for(int i = 0; i < arr.length; i++){
            if(arr[i] < number){
                i = i + 1;
                System.out.println("Our place in race: " + i);
                thePlaceIsFound = true;
                break;
            }
        }

        if(thePlaceIsFound == false){
            System.out.println("Our place in race: " + arr.length + 1);
        }
    }
}
```

```java
public class Main {
  public static void main(String[] args) {
    int[] arr = {8, 7, 5, 3, 2, 1}; // current race result
    int number = 4; // our result
    int place = getThePlace(arr, number);
    System.out.println("Our place in race: " + place);
 }

  public static int getThePlace(int[] arr, int number){
    for(int i = 0; i < arr.length; i++){
      if(arr[i] < number){
        return i + 1;
                  }
              }
  return arr.length + 1;
          }
      }
````

## Detect prime numbers?
e.g. 11

1.	Modulus function
2.	For Loop
3.	We can’t divide by any number between 1 and 11
4.	Make sure its not dividable by 2-10
5.	For loop that goes from 2 to 10 and if condition that used modulus 
11 % 2 != 0
11 % 3 != 0
11 % 4 != 0
11 % 5 != 0
11 % 6 != 0

Ieva: while loop until the first number for which %number ==0 not all, just up to half of 11!


## Polindrome (how to detect it?)
Aka
Anna
Öötöö
Radar

1.	Reverse the word and check if the original and reversed are the same. 
Different solution
1.	Use a for loop and go letter by letter
2.	First letter is the same as the last letter
3.	The second letter is the same as second last letter. 
4.	Int length = a length of the string
Length = 4
[“a”, “n”, “n”, “a”]
a.	Array [0] == array [3]
b.	Array [1] == array [2]
c.	Array [2] == array [1]
d.	Array [3] == array [0]
Length = 3
[“a”, “k”, “a”]
a.	Array [0] == array [2]
b.	Array [1] == array [1]

21 sticks game
2 players
Take 1 or 2 sticks in turns
Which one takes the last stick, loses. 
Develop a program, that can always win, when given a chance

1.	A player can pick number 1 or 2
2.	if there are 2-3 sticks left, the second player loses
3.	If there are 5-6 sticks, then we can force the other player to lose. 
4.	If there are 5 sticks, I need to take 1. 
5.	if 1 stick left, then player loses
6.	max amount of turns is 21
7.	1, 4, 7, 10, 13, 16, 19 – we need to force the other player to have this number of sticks, and then take the opposite of what the other player takes. 
8.	If the number is odd, we take 1 = if the number is even, we take 2. 
9.	The game goes in turns
10.	The game ends, when a person pulls out the last match  this means a while loop



 
## Hangman Word guessing game. 
6 tries to fail.
Decompose the problem
State the true facts about the game. 
Try and figure out, how a game is over (Instead of saying the word is guessed correctly; think about an array, and letters in there)

If guessed character in an array, then find all the instances.
If len 1 = len2 and indexes 0-x = 0-x, then word guessed 

Array 1 = array 2
CODE IT
At the end of each cycle check if there is a 0 element in it. An element is not given a value “ ”, later it is assigned a value. 
Original array = {“p”, “h”, “o”, “n”, “e”}
Guessing array = {“”, “”, “”, “”, “”}

Rock-paper-scissor game
Decompose the problem
Solve logical puzzles
Write winning/losing conditions

Paper beats rock
Rock beats Scissors
Scissors beats paper

Write down the conditions for a draw
Rock == rock
Paper == paper
Scissors == Scissors

1st time wins 
Best out of 3 wins
