
# Activity: Collections

## Objective

Identify palindrome and implement using deque 

## Pre-requisite

Review the "Collections" lecture before attending the lab. 

## Task

A palindrome is a string that reads the same backwards and forwards. Write a code which uses deque and tests whether a line of text is a palindrome. 
The program reads a line, then outputs whether the input is a palindrome or not.

__Expected input__

civic

__Expected output__

Yes, civic is a palindrome.

__Expected input__

rotostor

__Expected output__

No, "rotostor" is not a palindrome.

>**Note:** Ignore punctuation and spacing. Assume all alphabetic characters are lowercase.
>
>Special case: A one-character string is a palindrome.
>
>Hint: The deque must be a Deque of Characters, but ordinary chars will be automatically converted to Characters when added to the deque.

## Code
```java
import java.util.HashMap;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scnr = new Scanner(System.in);
        HashMap<Character, Integer> letter = new HashMap<>();

        System.out.print("Please enter a word: ");
        String word = scnr.nextLine();

        for (int i = 0; i < word.length(); i++) {
            char c = word.charAt(i);
            letter.put(c, letter.getOrDefault(c, 0) + 1);
        }
        
        System.out.println("Hashmap: " + letter);
        
        int oddCount = 0;
        for (int count : letter.values()) {
            if (count % 2 != 0) {
                oddCount++;
            }
        }
        
        System.out.println("Odd Count: " + oddCount);
        
        if (oddCount <= 1) {
            System.out.println("This is a palindrome");
        } else {
            System.out.println("This is not a palindrome");
        }
    }
}

```

## Flowchart Explaination
![image](https://github.com/user-attachments/assets/24ac6937-49a8-4dbb-8612-b76e292ef6de)

## Challenges
Finding a way to reliably figure out if a word was a palindrome was a difficult problem. The logic behind finding the amount of odd characters in the palindrome
took a bit of thinking, since it is not so obvious when you look at a palindrome that there cannot be more than one odd amount of characters. Writing up the logic
was not too complex after coming to this realization.

## Video Explaination
https://github.com/user-attachments/assets/8ac036bd-821d-4dbb-a5cb-fc2fbd975783


