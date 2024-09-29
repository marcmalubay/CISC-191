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
// ===== Code from file Person.java =====
public class Person {
   private int ageYears;
   private String lastName;

   public void setName(String userName) {
      lastName  = userName;
   }

   public void setAge(int numYears) {
      ageYears = numYears;
   }

   // Other parts omitted

   public void printAll() {
      System.out.print("Name: " + lastName);
      System.out.print(", Age: "  + ageYears);
   }
}

// ===== Code from file Student.java =====
public class Student extends Person {
   private int idNum;

   public void setID(int studentId) {
      idNum = studentId;
   }

   public int getID() {
      return idNum;
   }
}

// ===== Code from file StudentDerivationFromPerson.java =====
public class StudentDerivationFromPerson {
   public static void main(String[] args) {
      Student courseStudent = new Student();
      Person coursePerson = new Person();

      coursePerson.setName("Smith");
      coursePerson.setAge(20);
      coursePerson.printAll();
      courseStudent.setID(9999);
      System.out.println(", ID: " + courseStudent.getID());

   }
}
```
## Flowchart Explaination
![image](https://github.com/user-attachments/assets/6545de8a-55e5-4af4-882a-865204022f8a)


## Challenges
Setting up two different classes but having one derive from another was a challenge at first. Deriving two different classes did not make sense to me at first since I thought why would I need to do that if I can make another separate class that is its own. I figured out however that it is useful to divide classes into subclasses since it is easy to declare the same methods from a subclass rather than creating an identical class that has the same methods. It is simple to set up and allows for much cleaner programming.

## Video Explaination
https://github.com/user-attachments/assets/36f0119d-0425-45b8-be84-9daa40970aa8

