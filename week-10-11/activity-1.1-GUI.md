# Activity: GUI input and ActionListeners

## Objective

Write a code that takes user input and performs calculations

## Pre-requisite

Review the [GUI](https://htmlpreview.github.io/?https://github.com/d-khan/java/blob/main/gui/Lecture.html) lecture before attending the lab.

## Task

Take two user inputs using a JTextField, and display the yearly salary.

__Expected input__

Hourly wage and number of hours per week

__Expected output__

Yearly salary

## Code
```java
import javax.swing.*;
import javax.swing.border.LineBorder;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class Main {
    public static void main(String[] args) {
        JFrame frame = new JFrame("Yearly Salary Calculator");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(600, 500);

        frame.setLayout(new GridBagLayout());
        GridBagConstraints gbc = new GridBagConstraints();

        Color backgroundColor = new Color(45, 45, 45);
        Color textColor = new Color(220, 220, 220);
        Color buttonColor = new Color(60, 63, 65);
        Color borderColor = new Color(100, 100, 100);

        frame.getContentPane().setBackground(backgroundColor);

        gbc.insets = new Insets(4, 4, 4, 4);
        gbc.anchor = GridBagConstraints.CENTER;

        // Wage input
        JLabel wageLabel = new JLabel("Hourly Wage:");
        wageLabel.setForeground(textColor);
        gbc.gridx = 0;
        gbc.gridy = 0;
        gbc.gridwidth = 1;
        frame.add(wageLabel, gbc);

        JTextField wageField = new JTextField(10);
        wageField.setBackground(buttonColor);
        wageField.setForeground(textColor);
        wageField.setBorder(new LineBorder(borderColor, 1));
        gbc.gridx = 1;
        gbc.gridy = 0;
        frame.add(wageField, gbc);

        JLabel hoursLabel = new JLabel("Hours per Week:");
        hoursLabel.setForeground(textColor);
        gbc.gridx = 0;
        gbc.gridy = 1;
        frame.add(hoursLabel, gbc);

        JTextField hoursField = new JTextField(10);
        hoursField.setBackground(buttonColor);
        hoursField.setForeground(textColor);
        hoursField.setBorder(new LineBorder(borderColor, 1));
        gbc.gridx = 1;
        gbc.gridy = 1;
        frame.add(hoursField, gbc);


        JButton calculateButton = new JButton("Calculate Salary");
        calculateButton.setBackground(buttonColor);
        calculateButton.setForeground(textColor);
        calculateButton.setBorder(new LineBorder(borderColor, 1));

        gbc.gridx = 0;
        gbc.gridy = 2;
        gbc.gridwidth = 2;
        frame.add(calculateButton, gbc);

        JLabel resultLabel = new JLabel("Yearly Salary: $");
        resultLabel.setForeground(textColor);
        gbc.gridx = 0;
        gbc.gridy = 3;
        gbc.gridwidth = 2;
        gbc.anchor = GridBagConstraints.CENTER;
        frame.add(resultLabel, gbc);

        calculateButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                try {
                    double hourlyWage = Double.parseDouble(wageField.getText());
                    double hoursPerWeek = Double.parseDouble(hoursField.getText());
                    double yearlySalary = hourlyWage * hoursPerWeek * 52;

                    String numString = String.format("%,.2f", yearlySalary);
                    resultLabel.setText("Yearly Salary: $" + numString);
                } catch (NumberFormatException ex) {
                    resultLabel.setText("Please enter valid numbers.");
                }
            }
        });

        frame.setVisible(true);
    }
}
```
## Flowchart Explaination 
![image](https://github.com/user-attachments/assets/be9af415-3e2a-4d41-8b9b-5de65ca93ba8)

## Challenges
Centering all the pieces inside of the GridBagLayout was tricky for me. I wanted the calculate button and yearly salary label to be centered within the 
grid, but I did not know how to fit them in a spot that is in the middle. I first tried making the grid 3x2, making the pieces fall in the middle slot. 
This only ended up making the entire GUI look messy and I decided this was not the right decision. I then found out that you could stretch each piece
on the x or y axis, so I stretched both the calculate button and yearly salary label to be 2 wide. This allowed them to fit a slot in the middle.

## Video

Uploading activity-10.1-GUI.mp4…


