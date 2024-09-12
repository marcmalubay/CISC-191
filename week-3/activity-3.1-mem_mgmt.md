## Objective
Understand how memory management works in Java

## Pre-requisite
Review "Memory management"

## Task A (using classes)
Create your own class which performs a certain task. Use main() to create an object of the class. You can also use any past object and classes
examples.

## Expected output
The code and the mapping of each variable and object into "Stack and Heap". Make sure to show how garbage collector works on the code.
You can draw "Stack and Heap" on paper or on a computer. Your choice.
 
### Main
```java
public class MyClass
{
    public static void main(String[] args) {
        int myInt; // Stack
        Integer myInteger; // Heap
        
        myInt = 1; // Stack
        myInteger = new Integer(2); // Heap
        
        NewClass c = new NewClass();
        
        myInt = c.changeInt(myInt); // Stack
        myInteger = c.changeInteger(myInteger); // Heap
    }
}
```
### Class
```java
public class NewClass{
    int newInt; // Stack
    Integer newInteger; // Heap
    
    public NewClass() {
         newInt = 10; // Stack
         newInteger = new Integer(20); // Heap
    }
    
    public int changeInt(int i) {
        return 100; // Stack
    }
    
    public Integer changeInteger(Integer i) {
        return new Integer(200); // Heap
    }
}
```

### Stack
|Memory Address|Content|Variable|
| --- | --- | --- |
|1A|100|myInt|
|1B|2A|myInteger|
|1C|10|newInt|
|1D|2B|newInteger|

### Heap
|Memory Address|Content|Variable|
| --- | --- | --- |
|2A|200|myInteger|
|2B|20|newInteger|
|2C|||
|2D|||

### Flowchart Explaination
![image](https://github.com/user-attachments/assets/e7c7cb76-b083-4b61-8c67-8ba522e4344a)

### Challenges
I am still not 100% in my knowledge of how memory works in Java, but this is a suitable explanation for storing variables and information. For my solution I chose to write very basic code that assigns numbers to variables, but the purpose was to illustrate how the data is stored in the stack and heap. This solution does not explain garbage collection however, which I do not believe it needs to since the code is short and will not store many variables.
