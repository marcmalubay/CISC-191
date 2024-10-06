# Activity: Exceptions

## Objective

Create Step counter exceptions

## Pre-requisite

Review the "Exceptions" lecture before attending the lab. 

## Task

A pedometer treats walking 2,000 steps as walking 1 mile. Write a stepsToMiles() method that takes the number of steps as an integer parameter and returns the miles walked as a double. The stepsToMiles() method throws an Exception object with the message "Exception: Negative step count entered." when the number of steps is negative. Complete the main() method that reads the number of steps from a user, calls the stepsToMiles() method, and outputs the returned value from the stepsToMiles() method. Use a try-catch block to catch any Exception object thrown by the stepsToMiles() method and output the exception message.

Output each floating-point value with two digits after the decimal point, which can be achieved as follows:
`System.out.printf("%.2f", yourValue);`

__Expected input__

```
5345
```

__Expected output__

```Course Information:
2.67
```

**Expected input**

```
-3850
```

**Expected output**

```
Exception: Negative step count entered.
```

## Code
```java
import java.util.InputMismatchException;
import java.util.Scanner;

public class Main {
    public static double stepsToMiles(int n) throws Exception {
        if (n < 0.0) {
            throw new Exception("Exception: Negative step count entered.");
        }
        double miles = n;
        return (miles / 2000);
    }

    public static void main(String[] args) {
        Scanner scnr = new Scanner(System.in);
        int steps;
        double miles;

        System.out.print("Enter Number of Steps: ");
        try {
            steps = scnr.nextInt();

            try {
                miles = stepsToMiles(steps);
                System.out.printf("%.2f", miles);
            } catch (Exception e) {
                System.out.println(e.getMessage());
            }
        } catch (InputMismatchException e) {
            System.out.println("Integer input expected.");
        }
    }
}

```

## Flowchart Explaination
![image](https://github.com/user-attachments/assets/97d7eb3a-0563-485d-9b72-b80bb33f1a81)

## Challenges
It was difficult to grasp the concept of throwing and catching exceptions. To throw an exception there must also a catch. `throw new Exception()` cannot be declared 
without there being a way to catch the exception. I figured this issue out when I created a throw and catch in `main()`, but only threw an exception in `stepsToMiles()`. 
This resulted in the output reading the exception in `main()` on both occasions, rather than having two different messages. This led me to realize that main needs to have two 
sets of try-catch blocks, to handle the exception in `main` and handle the exception in `stepsToMiles()`.

## Video Explaination
https://github.com/user-attachments/assets/3b29d5da-d95b-41d5-8d4b-561812c55d62


