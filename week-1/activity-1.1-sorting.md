## Objective
Sort an array

## Task
Define a method named sortArray that takes an array of integers and the number of elements in the array as parameters. Method ```sortArray()``` modifies the array parameter by sorting the elements in descending order (highest to lowest). Then write a main program that reads a list of integers from input, stores the integers in an array, calls ```sortArray()```, and outputs the sorted array. The first input integer indicates how many numbers are in the list. Assume that the list will always contain less than 20 integers.
Your program must define and call the following method:  ```public static void sortArray(int[] myArr, int arrSize)```

## Example input
5 10 4 39 12 2

## Example output
39,12,10,4,2

## Code
```java
public class Main {
    public static void sortArray(int[] myArr, int arrSize) {
        boolean swap;

        for (int i = 0; i < arrSize - 1; i++){
            swap = false;

            for (int j = 0; j < arrSize - 1 - i; j++){
                if (myArr[j] > myArr[j + 1]){
                    swap = true;

                    int temp = myArr[j];
                    myArr[j] = myArr[j + 1];
                    myArr[j + 1] = temp;

                }
            }

            if (!swap) {
                break;
            }
        }
    }

    public static void main(String[] args) {
        int[] arr = {5,10,4,39,12,2};
        int arrSize = 6;
        
        System.out.print("This is my original array: ");
        for (int i = 0; i <= arrSize - 1; i++){
            if (i == 0){
                System.out.print("[" + arr[i] + ", ");
                continue;
            }
            
            if (i == arrSize - 1){
                System.out.println(arr[i] + "]");
                continue;
            }
            System.out.print(arr[i] + ", ");
        }
        
        
        sortArray(arr, arrSize);

        System.out.print("This is my sorted array: ");
        for (int i = 0; i <= arrSize - 1; i++){
            if (i == 0){
                System.out.print("[" + arr[i] + ", ");
                continue;
            }
            
            if (i == arrSize - 1){
                System.out.println(arr[i] + "]");
                continue;
            }
            System.out.print(arr[i] + ", ");
        }
    }
}
```

## Why I chose to use Bubble sort
This problem specifies that the maximum length of the array will be 20. This means that although bubble sort is not the most time-efficient algorithm, it will do the job for this problem since we do not really need to worry about time complexity. I also chose to use this algorithm because I am most familiar with bubble sort compared to others.

## Flowchart Explanation
![image](https://github.com/user-attachments/assets/b47152a1-642e-4a98-b49d-8b8d20c294c1)

## Challenges
Figuring out which algorithm to use was a challenge for me. I know that bubble sort is not the fastest algorithm to use since it is of O(N^2) complexity. I am not very familiar with other algorithms, so I chose what I was most comfortable working with. Finding a way to display the array with prints was quite difficult as well. It has been a while since I have had to work with printing in Java so I came up with a way to print my output, but I am sure there is better ways to go about this.

## Video Explanation
https://github.com/user-attachments/assets/76514995-e934-47e4-97f3-01bedfa9c723

