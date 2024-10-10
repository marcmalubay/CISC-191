## QUESTION 1

# Main
```java
import java.util.Scanner;

public class InventoryControl {
    public static void main(String[] args){
        Scanner scnr = new Scanner(System.in);
        System.out.print("Please input which item you are placing into inventory (Painkillers, Bandages, Equipment): ");

        String type = scnr.nextLine();

        System.out.print("Input name: ");
        String name = scnr.nextLine();
        System.out.print("Input company: ");
        String company = scnr.nextLine();
        Item item = new Item(name, company);

        if (type.equals("Painkillers")){
            System.out.print("Input Expiration Date: ");
            String exp = scnr.nextLine();
            System.out.print("Input Age Group: ");
            String ag = scnr.nextLine();
            Painkillers p = new Painkillers(name, company, exp, ag);
            p.displayItem();


        } else if (type.equals("Bandages")) {
            System.out.print("Input Expiration Date: ");
            String exp = scnr.nextLine();
            System.out.print("Input Age Group: ");
            String ag = scnr.nextLine();
            System.out.print("Input Water Proof: ");
            Boolean wp = scnr.nextBoolean();
            Bandages b = new Bandages(name, company, exp, ag, wp);
            b.displayItem();

        } else if (type.equals("Equipment")) {
            System.out.print("Input Weight: ");
            double weight = scnr.nextDouble();
            Equipment e = new Equipment(name, company, weight);
            e.displayItem();
        }
    }
}

```
# Item class
```java
public class Item {
    protected String name;
    protected String company;

    public Item(String name, String company){
        this.name = name;
        this.company = company;
    }

    public void updateItems(String name, String company){
        this.name = name;
        this.name = company;
    }

    public void displayItem(){
        System.out.println("    Name: " + name);
        System.out.println("    Company: " + company);
    }
}


```

# Painkillers Derived Class
```java
public class Painkillers extends Item{
    private String exp;
    private String ag;

    public Painkillers(String name, String company, String exp, String age_group){
        super(name, company);
        this.exp = exp;
        this.ag = age_group;
    }

    @Override
    public void displayItem(){
        System.out.println("Painkillers: ");
        System.out.println("    Name: " + name);
        System.out.println("    Company: " + company);
        System.out.println("    Expiration Date: " + exp);
        System.out.println("    Age Group: " + ag);
    }
}


```
# Bandages Derived Class
```java
public class Bandages extends Item{
    private String exp;
    private String age_group;
    private Boolean wp;

    public Bandages(String name, String company, String exp, String age_group, Boolean wp){
        super(name, company);
        this.exp = exp;
        this.age_group = age_group;
        this.wp = wp;
    }

    @Override
    public void displayItem(){
        System.out.println("Bandages: ");
        System.out.println("    Name: " + name);
        System.out.println("    Company:" + company);
        System.out.println("    Expiration Date: " + exp);
        System.out.println("    Age Group: " + age_group);
        System.out.println("    Water Proof: " + wp);
    }
}

```
# Equipment Derived Class
```java
public class Equipment extends Item{
    private double weight;

    public Equipment(String name, String company, double weight){
        super(name, company);
        this.weight = weight;
    }

    @Override
    public void displayItem(){
        System.out.println("Equipment: ");
        System.out.println("    Name: " + name);
        System.out.println("    Company: " + company);
        System.out.println("    Weight: " + weight);
    }
}

```
## Question 2

## Wrap a try and catch block around main
```java
import java.util.Scanner;
import java.util.InputMismatchException;

public class InventoryControl {
    public static void main(String[] args) throws Exception{
        Scanner scnr = new Scanner(System.in);
        System.out.print("Please input which item you are placing into inventory (Painkillers, Bandages, Equipment): ");

        String type = scnr.nextLine();

        System.out.print("Input Name: ");
        String name = scnr.nextLine();
        System.out.print("Input Company: ");
        String company = scnr.nextLine();
        Item item = new Item(name, company);

        try {
            if (type.equals("Painkillers")) {
                System.out.print("Input Expiration Date: ");
                String exp = scnr.nextLine();
                System.out.print("Input Age Group: ");
                String ag = scnr.nextLine();
                Painkillers p = new Painkillers(name, company, exp, ag);
                p.displayItem();


            } else if (type.equals("Bandages")) {
                System.out.print("Input Expiration Date: ");
                String exp = scnr.nextLine();
                System.out.print("Input Age Group: ");
                String ag = scnr.nextLine();
                System.out.print("Input Water Proof: ");
                Boolean wp = scnr.nextBoolean();
                Bandages b = new Bandages(name, company, exp, ag, wp);
                b.displayItem();

            } else if (type.equals("Equipment")) {
                System.out.print("Input Weight: ");
                double weight = scnr.nextDouble();
                Equipment e = new Equipment(name, company, weight);
                e.displayItem();
            }
        }
        catch(InputMismatchException e){
            System.out.println("Invalid Input");
        }
    }
}

```

## Question 3

## Create new method to check if input is valid
```java
    public static void validateInput(String input) throws Exception {
        if (!(input.equals("Painkillers") || input.equals("Bandages") || input.equals("Equipment"))) {
            throw new Exception("Invalid input. Please enter only 'Painkillers', 'Bandages', or 'Equipment'.");
        }
    }
```

## Wrap input around try and catch for the new thrown exception
```java
        String type = scnr.nextLine();
        try {
            validateInput(type);
        }catch(Exception e) {
            System.out.println(e.getMessage());
        }
```
## Final Code in Main (derived classes were not changed)
```java
import java.util.Scanner;
import java.util.InputMismatchException;

public class InventoryControl {
    public static void validateInput(String input) throws Exception {
        if (!(input.equals("Painkillers") || input.equals("Bandages") || input.equals("Equipment"))) {
            throw new Exception("Invalid input. Please enter only 'Painkillers', 'Bandages', or 'Equipment'.");
        }
    }

    public static void main(String[] args){
        Scanner scnr = new Scanner(System.in);

        System.out.print("Input Product Name: ");
        String name = scnr.nextLine();
        System.out.print("Input Product Company: ");
        String company = scnr.nextLine();
        Item item = new Item(name, company);

        System.out.print("Please input which item you are placing into inventory (Painkillers, Bandages, Equipment): ");

        String type = scnr.nextLine();
        try {
            validateInput(type);
        }catch(Exception e) {
            System.out.println(e.getMessage());
        }

        try {
            if (type.equals("Painkillers")) {
                System.out.print("Input Expiration Date: ");
                String exp = scnr.nextLine();
                System.out.print("Input Age Group: ");
                String ag = scnr.nextLine();
                Painkillers p = new Painkillers(name, company, exp, ag);
                p.displayItem();


            } else if (type.equals("Bandages")) {
                System.out.print("Input Expiration Date: ");
                String exp = scnr.nextLine();
                System.out.print("Input Age Group: ");
                String ag = scnr.nextLine();
                System.out.print("Input Water Proof: ");
                Boolean wp = scnr.nextBoolean();
                Bandages b = new Bandages(name, company, exp, ag, wp);
                b.displayItem();

            } else if (type.equals("Equipment")) {
                System.out.print("Input Weight: ");
                double weight = scnr.nextDouble();
                Equipment e = new Equipment(name, company, weight);
                e.displayItem();
            }
        }
        catch(InputMismatchException e){
            System.out.println("Invalid Input");
        }
    }
}

```
