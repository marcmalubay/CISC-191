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
