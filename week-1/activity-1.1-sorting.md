## Objective
Sort an array

## Task
Define a method named sortArray that takes an array of integers and the number of elements in the array as parameters. Method ```sortArray()``` modifies the array parameter by sorting the elements in descending order (highest to lowest). Then write a main program that reads a list of integers from input, stores the integers in an array, calls ```sortArray()```, and outputs the sorted array. The first input integer indicates how many numbers are in the list. Assume that the list will always contain less than 20 integers.
Your program must define and call the following method:  ```public static void sortArray(int[] myArr, int arrSize)```

## Example input
5 10 4 39 12 2

## Example output
39,12,10,4,2

## Answer
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
        sortArray(arr, arrSize);

        for (int i = 0; i <= arrSize - 1; i++){
            System.out.print(arr[i] + " ");


        }
    }
}
```
