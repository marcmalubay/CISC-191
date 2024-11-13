# Activity: Merge sort

## Objective

Write a code and implement merge sort

## Pre-requisite

Review the [Search and sort lecture](https://htmlpreview.github.io/?https://github.com/d-khan/java/blob/main/search-sort/Lecture.html)

## Task
- Read the size of an integer array, followed by the elements of the array (no duplicates).
- Output the array.
- Perform an merge sort on the array.
- Output the number of comparisons and swaps performed.

__Expected input__

`6 3 2 1 5 9 8`

__Expected output__

```
unsorted: 3 2 1 5 9 8

sorted:   1 2 3 5 8 9
comparisons: 8
```
## Code

```java
import java.util.Scanner;

public class Main {

    private static int comparisons = 0;

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Input Array Size: ");
        int n = scanner.nextInt();

        System.out.println("Input Array Elements: ");
        int[] array = new int[n];
        for (int i = 0; i < n; i++) {
            array[i] = scanner.nextInt();
        }

        System.out.print("unsorted: ");
        printArray(array);

        mergeSort(array, 0, array.length - 1);

        System.out.print("sorted: ");
        printArray(array);
        System.out.println("comparisons: " + comparisons);

        scanner.close();
    }

    private static void mergeSort(int[] array, int left, int right) {
        if (left < right) {
            int mid = left + (right - left) / 2;

            mergeSort(array, left, mid);
            mergeSort(array, mid + 1, right);

            merge(array, left, mid, right);
        }
    }

    private static void merge(int[] array, int left, int mid, int right) {
        int n1 = mid - left + 1;
        int n2 = right - mid;

        int[] leftArray = new int[n1];
        int[] rightArray = new int[n2];

        for (int i = 0; i < n1; i++)
            leftArray[i] = array[left + i];
        for (int i = 0; i < n2; i++)
            rightArray[i] = array[mid + 1 + i];

        int i = 0, j = 0;
        int k = left;
        while (i < n1 && j < n2) {
            comparisons++;
            if (leftArray[i] <= rightArray[j]) {
                array[k] = leftArray[i];
                i++;
            } else {
                array[k] = rightArray[j];
                j++;
            }
            k++;
        }

        while (i < n1) {
            array[k] = leftArray[i];
            i++;
            k++;
        }

        while (j < n2) {
            array[k] = rightArray[j];
            j++;
            k++;
        }
    }

    private static void printArray(int[] array) {
        for (int value : array) {
            System.out.print(value + " ");
        }
        System.out.println();
    }
}

```
## Flowchart Explaination
![image](https://github.com/user-attachments/assets/1d7f1785-6ac3-409d-9851-0499401ea054)

## Challenges
I often struggle with programming recursions. It can be easy to lose track of what the code is doing at a certain
point and it is hard to debug. Recursions are a big part of merge sort, since the function must recursively divide
and sort an array until each element is in its correct place. This means that this is a divide-and-conquer solution.
As long as you can understand how each step of the recursion works, this problem becomes not so difficult to understand.

## Video Explaination
https://github.com/user-attachments/assets/54dd4d8a-68a2-4edb-8d28-c1eb2ee19bcc


