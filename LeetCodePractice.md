# Assignment 1
Given a string s, find the length of the longest substring without repeating characters.

### Example 1:
Input: s = "abcabcbb"
Output: 3
Explanation: The answer is "abc", with the length of 3.

### Example 2:
Input: s = "bbbbb"
Output: 1
Explanation: The answer is "b", with the length of 1.

### Example 3:
Input: s = "pwwkew"
Output: 3
Explanation: The answer is "wke", with the length of 3.

Notice that the answer must be a substring, "pwke" is a subsequence and not a substring.
### Constraints:
0 <= s.length <= 5 * 104
s consists of English letters, digits, symbols and spaces.

```java
import java.util.HashMap;
import java.util.Scanner;

class Solution {
    public static int lengthOfLongestSubstring(String s) {
        HashMap<Character, Integer> charIndexMap = new HashMap<>();
        int maxLength = 0;
        int left = 0;

        // Sliding window with HashMap to store the last occurrence of each character
        for (int right = 0; right < s.length(); right++) {
            char currentChar = s.charAt(right);

            // If the character is already in the map and within the current window
            if (charIndexMap.containsKey(currentChar) && charIndexMap.get(currentChar) >= left) {
                // Move the left pointer to the right of the previous occurrence of the character
                left = charIndexMap.get(currentChar) + 1;
            }

            // Update the character's last seen index
            charIndexMap.put(currentChar, right);

            // Update maxLength if we found a longer substring
            maxLength = Math.max(maxLength, right - left + 1);
        }

        return maxLength;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        // Prompt the user for input
        System.out.print("Enter a string: ");
        String inputString = scanner.nextLine();
        
        // Call the function and print the result
        int result = lengthOfLongestSubstring(inputString);
        System.out.println("Length of the longest substring without repeating characters: " + result);
        
        scanner.close();
    }
}
```

# Assignment 2
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */

Midagi erroris...

```java
public class Solution {

    // Definition for singly-linked list.
    public static class ListNode {
        int val;
        ListNode next;
        ListNode(int val) {
            this.val = val;
            this.next = null;
        }
    }

    public static ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        // Create a dummy node to simplify result handling
        ListNode dummyHead = new ListNode(0);
        ListNode current = dummyHead;
        int carry = 0;

        // Loop until both l1 and l2 are exhausted and no carry is left
        while (l1 != null || l2 != null || carry != 0) {
            // Get the values from the nodes, or 0 if the list is exhausted
            int x = (l1 != null) ? l1.val : 0;
            int y = (l2 != null) ? l2.val : 0;
            
            // Calculate the sum of the two digits and the carry
            int sum = x + y + carry;
            
            // Update the carry for the next iteration
            carry = sum / 10;
            
            // Create a new node with the current digit (sum % 10)
            current.next = new ListNode(sum % 10);
            current = current.next;
            
            // Move to the next nodes in both lists
            if (l1 != null) l1 = l1.next;
            if (l2 != null) l2 = l2.next;
        }

        // The result starts at dummyHead.next
        return dummyHead.next;
    }

    // Helper function to print the linked list
    public static void printList(ListNode node) {
        while (node != null) {
            System.out.print(node.val);
            if (node.next != null) System.out.print(" -> ");
            node = node.next;
        }
        System.out.println();
    }

   public class Driver {
    public static void main(String[] args) {
        // Create the linked lists l1 = [2,4,3] and l2 = [5,6,4]
        Solution.ListNode l1 = new Solution.ListNode(2);
        l1.next = new Solution.ListNode(4);
        l1.next.next = new Solution.ListNode(3);

        Solution.ListNode l2 = new Solution.ListNode(5);
        l2.next = new Solution.ListNode(6);
        l2.next.next = new Solution.ListNode(4);

        // Call addTwoNumbers from Solution class
        Solution.ListNode result = Solution.addTwoNumbers(l1, l2);

        // Print the result
        Solution.printList(result); // Output: 7 -> 0 -> 8
    }
}
```
