# Inheritance

## Objective
Understand how subclasses and derived from the superclass.

## Pre-requisite
Review the "Inheritance" lecture before attending the lab. 

## Task
Assign courseStudent's name with Smith, age with 20, and ID with 9999. Use the printAll() member method and a separate println() statement to output courseStudents's data. 

## Expected output
```Name: Smith, Age: 20, ID: 9999```

## Solution
```java
// ===== Code from file StudentDerivationFromPerson.java =====
public class StudentDerivationFromPerson {
   public static void main(String[] args) {
       Person coursePerson = new Person();
       Student courseStudent = new Student();

       coursePerson.setName("Smith");
       coursePerson.setAge(20);
       coursePerson.printAll();
       courseStudent.setID(9999);
       System.out.println(", ID: " + courseStudent.getID());

   }
}
```
## Video Explaination
https://github.com/user-attachments/assets/36f0119d-0425-45b8-be84-9daa40970aa8

