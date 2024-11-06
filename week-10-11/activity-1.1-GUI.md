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

        // Set the layout manager for the frame
        frame.setLayout(new GridBagLayout());
        GridBagConstraints gbc = new GridBagConstraints();

        // Set dark mode colors
        Color backgroundColor = new Color(45, 45, 45);  // Dark background
        Color textColor = new Color(220, 220, 220);     // Light text color
        Color buttonColor = new Color(60, 63, 65);      // Darker button color
        Color borderColor = new Color(100, 100, 100);   // Light gray border color

        // Apply the background color to the frame
        frame.getContentPane().setBackground(backgroundColor);

        // Center all elements both horizontally and vertically
        gbc.insets = new Insets(4, 4, 4, 4);  // Padding around components
        gbc.anchor = GridBagConstraints.CENTER;   // Center alignment

        // Wage input
        JLabel wageLabel = new JLabel("Hourly Wage:");
        wageLabel.setForeground(textColor); // Set text color for dark mode
        gbc.gridx = 0;
        gbc.gridy = 0;
        gbc.gridwidth = 1;
        frame.add(wageLabel, gbc);

        JTextField wageField = new JTextField(10);
        wageField.setBackground(buttonColor); // Set field background for dark mode
        wageField.setForeground(textColor); // Set field text color for dark mode
        wageField.setBorder(new LineBorder(borderColor, 1)); // Set custom border color
        gbc.gridx = 1;
        gbc.gridy = 0;
        frame.add(wageField, gbc);

        // Hours input
        JLabel hoursLabel = new JLabel("Hours per Week:");
        hoursLabel.setForeground(textColor);
        gbc.gridx = 0;
        gbc.gridy = 1;
        frame.add(hoursLabel, gbc);

        JTextField hoursField = new JTextField(10);
        hoursField.setBackground(buttonColor);
        hoursField.setForeground(textColor);
        hoursField.setBorder(new LineBorder(borderColor, 1)); // Set custom border color
        gbc.gridx = 1;
        gbc.gridy = 1;
        frame.add(hoursField, gbc);

        // Calculate button
        JButton calculateButton = new JButton("Calculate Salary");
        calculateButton.setBackground(buttonColor);
        calculateButton.setForeground(textColor);
        calculateButton.setBorder(new LineBorder(borderColor, 1)); // Set custom border color

        gbc.gridx = 0;
        gbc.gridy = 2;
        gbc.gridwidth = 2;  // Span both columns
        frame.add(calculateButton, gbc);

        // Result label
        JLabel resultLabel = new JLabel("Yearly Salary: $");
        resultLabel.setForeground(textColor);
        gbc.gridx = 0;
        gbc.gridy = 3;
        gbc.gridwidth = 2;  // Span both columns
        gbc.anchor = GridBagConstraints.CENTER;
        frame.add(resultLabel, gbc);

        // Action listener for the calculation
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
