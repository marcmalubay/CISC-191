# Derived classes

## Objective
Use inheritance to store user data.

## Pre-requisite
Review the "Inheritance" lecture before attending the lab. 

## Task
Write `main()`, define a `Course` base class with methods to set and get private fields of the following types:

- String to store the course number
- String to store the course title

Define `Course`'s PrintInfo() method that outputs the course number and title.

Then, define a derived class `OfferedCourse` with methods to set and get private fields of the following types:

- String to store the instructor's name
- String to store the location
- String to store the class time

## Expected input
```
ECE287
Digital Systems Design
ECE387
Embedded Systems Design
Mark Patterson
Wilson Hall 231
WF: 2-3:30 pm
```
## Expected output
```Course Information:
Course Information:
   Course Number: ECE287
   Course Title: Digital Systems Design
Course Information:
   Course Number: ECE387
   Course Title: Embedded Systems Design
   Instructor Name: Mark Patterson
   Location: Wilson Hall 231
   Class Time: WF: 2-3:30 pm
```
## Code

## Course class
```java
public class Course {
   protected String courseNumber;
   protected String courseName;

   public void setNumber(String n) {
      courseNumber = n;
   }

   public void setName(String n) {
      courseName = n;
   }

   public void printInfo() {
      System.out.println("Course Information:");
      System.out.println("  Course Number: "  + courseNumber);
      System.out.println("  Course Name: "  + courseName);
   }
}
```

## OfferedCourse class
```java
public class OfferedCourse extends Course {
    private String instructorName;
    private String location;
    private String time;

    public void setInstructor(String n) {
        instructorName = n;
    }
    
    public void setLocation(String n) {
        location = n;
    }


    public void setTime(String n) {
        time = n;
    }

    public void printInfo() {
        System.out.println("Course Information:");
        System.out.println("    Course Number: "  + courseNumber);
        System.out.println("    Course Name: "  + courseName);
        System.out.println("    Course Instructor: "  + courseNumber);
        System.out.println("    Course Location: "  + courseName);
        System.out.println("    Course Time: "  + courseName);
   }
}
```

## Main class
```java
public class Main {
   public static void main(String[] args) {
       Course course = new Course();
       OfferedCourse offeredCourse = new OfferedCourse();

       course.setNumber("ECE287");
       course.setName("Digital Systems Design");
       course.printInfo();
       offeredCourse.setNumber("ECE387");
       offeredCourse.setName("Embedded Systems Design");
       offeredCourse.setInstructor("Mark Patterson");
       offeredCourse.setLocation("Wilson Hall 231");
       offeredCourse.setTime("WF: 2-3:30 pm");
       offeredCourse.printInfo();

   }
}
```
