## Objective

Write a code to access and manipulate databases using MySQL J connector

## Pre-requisite

- Review the [Databases](https://htmlpreview.github.io/?https://github.com/d-khan/java/blob/main/databases/Lecture.html) lecture.
- Perform the [practice lab](https://github.com/d-khan/java/blob/main/databases/Practice-lab.md).

## Task
- Manipulate the record in the already created database __Miramar__ and the table __Student__.
- Insert a record using the J connector; access the database and use SQL query inside the Java. Use the following data.
```
SSN:          111222333
First name:   Philip
Middle name:  David Charles
Last name:    Collins
DOB:          Jan 30, 1951
Street:       NA
Phone:        NA
Zipcode:      NA
deptID:       1234
```
- Update a record and change zip code to 92126

```java
import java.sql.*;
import java.util.Scanner;

public class Main {
    public static void main(String[] args)
            throws SQLException, ClassNotFoundException {
        // connect root@localhost:3306
        Scanner myObj = new Scanner(System.in);

        // Load the JDBC driver
        Class.forName("com.mysql.cj.jdbc.Driver");
        System.out.println("Driver loaded");

        Connection connection = DriverManager.getConnection
                ("jdbc:mysql://localhost/miramar","testuser","Pa$$word");
        System.out.println("Database connected");

        Statement statement = connection.createStatement();
        ResultSet resultSet = statement.executeQuery("select * from student;");
        ResultSetMetaData metaData = resultSet.getMetaData();

        int columnCount = metaData.getColumnCount();

        while (resultSet.next())
            for (int i = 1; i <= columnCount; i++) { // Loop through each column
                String value = resultSet.getString(i);
                if (value == null) {
                    System.out.println((metaData.getColumnName(i) + " is empty, please input a new value. (Max input is ") + (metaData.getPrecision(i)) + ")" + "\t");
                    String newVal = myObj.nextLine();

                    String updateQuery = "UPDATE student SET " + metaData.getColumnName(i) + " = ? WHERE ssn = ?";

                    try (PreparedStatement preparedStatement = connection.prepareStatement(updateQuery)) {
                        preparedStatement.setString(1, newVal);
                        preparedStatement.setString(2, "111222333"); // Example condition; replace with a variable if needed
                        int rowsUpdated = preparedStatement.executeUpdate();

                        if (rowsUpdated > 0) {
                            System.out.println("Updated successfully!");
                        } else {
                            System.out.println("Update failed!");
                        }
                    }
                } else {
                    System.out.println(metaData.getColumnName(i) + "\t" + value);
                }
            }
        System.out.println();

        // Close the connection
        connection.close();
    }
}

```
## Flowchart Explaination
![image](https://github.com/user-attachments/assets/2107e264-d1bd-4f9f-9b5a-b9d444d814bf)

## Challenges
Using prepared statments and utilizing metadata was difficult for me. I needed to find a way to find the name of the column and the max values, and I found that
you are able to use metadata in order to do that. I do not understand why the resultset is unable to do this, but I was still able to access all the data I needed 
to using metadata. Prepared statements also was difficult to implement. Using a prepared statement allows for the user to only input the correct input that I want.
This allows for no SQL injections and all around safer code. I wanted to try this out for this assignment and it took a while to understand, but I got it done in the end.

## Video Explaination

