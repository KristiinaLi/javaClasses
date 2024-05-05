
```java
import java.util.Scanner;
import java.util.Random;

public class Main {
  public static void main(String[] args) {
    Random random = new Random();
    Scanner scanner = new Scanner(System.in);

    System.out.println("This program will draw beautiful trees for you.");
    System.out.print("\nHow many trees would you like to have?  ");
    int numTrees = scanner.nextInt();
    scanner.close();

// Select random heights for the trees    
    int[] height = new int[numTrees];
    for(int i = 0; i < numTrees; i++) {
      height[i] = random.nextInt(8) + 3; 
      }
/*the random.nextInt(8) would provide an integer in the range 0-7. I want the trees to be in the range 3-10, so add 3
        */
      
// Select random characters as leaves for each of the trees  
    String[] leaf = new String[numTrees];
    String characters = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789<>?!@#$%^&*()_+-=[]{}|;:,./";
    for(int i = 0; i < numTrees; i++) {
      int index = random.nextInt(characters.length());
      leaf[i] = String.valueOf(characters.charAt(index));
    }

    int tallest = height[0];
    for(int i = 1; i < numTrees; i++) {
      tallest = Math.max(tallest, height[i]);
    }

    System.out.println("\nHere are your trees. Merry Christmas!");
    String[] forest = new String[tallest + 2];
    for(int i = 0; i < tallest + 2; i++){
      forest[i] = "";
    }
    String space = " ";
    for(int i = 0; i < numTrees; i++) {
      for(int j = 0; j < tallest + 2; j++) {
        String[] tree = treeCreator(tallest, height[i], leaf[i], space);
        forest[j] += tree[j];
      }
    }
    for(int i = 0; i < tallest + 2; i++) {
      System.out.println(forest[i]);
    }
  }
  public static String[] treeCreator(int tallest, int height, String leaf, String space) {
      String[] tree = new String[tallest + 2];
      for(int i = 0; i <= tallest - height; i++){
        tree[i] = space.repeat(2 * height);
      }
      for(int i = tallest - height + 1; i <= tallest; i++) {
        int k = i - (tallest - height);
        tree[i] = space.repeat(height - k + 1) + leaf.repeat(2 * k - 1) + space.repeat(height - k);
      }
      tree[tallest + 1] = space.repeat(height) + "|" + space.repeat(height - 1);
      return tree;
    }
  }
  ```
