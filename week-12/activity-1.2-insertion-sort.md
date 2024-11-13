# Activity: Insertion sort

## Objective

Write a code and implement insertion sort

## Pre-requisite

Review the [Search and sort lecture](https://htmlpreview.github.io/?https://github.com/d-khan/java/blob/main/search-sort/Lecture.html)

## Task
- Read the size of an integer array, followed by the elements of the array (no duplicates).
- Output the array.
- Perform an insertion sort on the array.
- Output the number of comparisons and swaps performed.

__Expected input__

`6 3 2 1 5 9 8`

__Expected output__

```
3 2 1 5 9 8

2 3 1 5 9 8
1 2 3 5 9 8
1 2 3 5 9 8
1 2 3 5 9 8
1 2 3 5 8 9

comparisons: 7
swaps: 4
```

## Code
```java
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.print("Input size of Array: ");
        int n = scanner.nextInt();
        
       
        System.out.println("Input array elements: ");
        int[] arr = new int[n];
        for (int i = 0; i < n; i++) {
            arr[i] = scanner.nextInt();
        }
        
        printArray(arr);

        int comparisons = 0;
        int swaps = 0;

        for (int i = 1; i < n; i++) {
            int key = arr[i];
            int j = i - 1;
            
            while (j >= 0 && arr[j] > key) {
                comparisons++;
                arr[j + 1] = arr[j];
                j--;
                swaps++;
            }
            if (j >= 0) {
                comparisons++;
            }

            arr[j + 1] = key;

            printArray(arr);
        }

        System.out.println("comparisons: " + comparisons);
        System.out.println("swaps: " + swaps);
    }

    private static void printArray(int[] arr) {
        for (int num : arr) {
            System.out.print(num + " ");
        }
        System.out.println();
    }
}

```

## Flowchart Explaination
![image](https://github.com/user-attachments/assets/51e96e90-4e1c-49f7-90de-0ffdbf5f24e7)

## Challenges
This assignment was simple to understand, but hard to program. The while loop inside of the for loop didnt make
sense to me at first. I did not understand whow comparisons and swaps were doing. Comparisons are made to find the 
correct position between two elements to find the correct positions, and swaps move those elements to those positons.
Elements can be compared multiple times in one pass, while they can be swapped only one or none per pass.

## Video Explanation
https://github.com/user-attachments/assets/bbc4ef40-e869-4fbb-880e-53710626bf46

