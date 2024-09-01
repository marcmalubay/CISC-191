## Objective
Understand how to apply classes and constructors

## Task A (using classes)
The program below uses a class, TaxTableTools, which has a tax table built in. The main method prompts for a salary, then uses a TaxTableTools method to get the tax rate. The program then calculates the tax to pay and displays the results to the user. Run the program with annual salaries of 10000, 50000, 50001, 100001 and -1 (to end the program) and note the output tax rate and tax to pay.

1. Modify the TaxTableTools class to use a setter method that accepts a new salary and tax rate table.   
2. Modify the program to call the new method, and run the program again, noting the same output.   

## Main IncomeTaxMain
```java
table.setTables(salary, taxTable);
```

## Class TaxTableTools
```java
public void setTables(int[] salary, double[] table) {
    search = salary;
    value = table;
}
```
## Task B (using constructor overload)
The program below calculates a tax rate and tax to pay given an annual salary. The program uses a class, TaxTableTools, which has the tax table built in. Run the program with annual salaries of 10000, 50000, 50001, 100001 and -1 (to end the program) and note the output tax rate and tax to pay.

1. Overload the constructor.   
   - Add to the TaxTableTools class an overloaded constructor that accepts the base salary table and corresponding tax rate table as parameters.   
   - Modify the main method to call the overloaded constructor with the two tables (arrays) provided in the main method. Be sure to set the nEntries value, too.  
   - Note that the tables in the main method are the same as the tables in the TaxTableTools class. This sameness facilitates testing the program with the same annual salary values listed above.  
   - Test the program with the annual salary values listed above.
2. Modify the salary and tax tables
   - Modify the salary and tax tables in the main method to use different salary ranges and tax rates.
   - Use the just-created overloaded constructor to initialize the salary and tax tables.
   - Test the program with the annual salary values listed above.
## Main IncomeTaxMain
```java
TaxTableTools table = new TaxTableTools(salaryRange, taxRates);
```

## Class TaxTableTools
```java
public TaxTableTools(int[] s, double[] t) {
    search = s;
    value = t;
    nEntries = search.length;
}
```


## Flowchart Explanation
![image](https://github.com/user-attachments/assets/126ee917-0a1e-4373-814a-a33ff41bd1f6)

## Challenges
Figuring out which algorithm to use was a challenge for me. I know that bubble sort is not the fastest algorithm to use since it is of O(N^2) complexity. I am not very familiar with other algorithms, so I chose what I was most comfortable working with. Finding a way to display the array with prints was quite difficult as well. It has been a while since I have had to work with printing in Java so I came up with a way to print my output, but I am sure there is better ways to go about this.

## Video Explanation
https://github.com/user-attachments/assets/76514995-e934-47e4-97f3-01bedfa9c723
