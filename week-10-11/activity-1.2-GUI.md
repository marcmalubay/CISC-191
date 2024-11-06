## Objective

Write a code that takes user input and performs calculations

## Pre-requisite

Review the [GUI](https://htmlpreview.github.io/?https://github.com/d-khan/java/blob/main/gui/Lecture.html) lecture before attending the lab.

## Task

Take a single user input using a JFormattedTextField, and display multiple results.

__Expected input__

Take distance (in miles)

__Expected output__

Display results in (km, m, feet)

### Code
```java
import javax.swing.*;
import javax.swing.border.LineBorder;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.text.NumberFormat;

public class Main {
    public static void main(String[] args) {
        JFrame frame = new JFrame("Distance Converter");
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

        JLabel distanceLabel = new JLabel("Distance (in miles):");
        distanceLabel.setForeground(textColor);
        gbc.gridx = 0;
        gbc.gridy = 0;
        gbc.gridwidth = 1;
        frame.add(distanceLabel, gbc);

        NumberFormat format = NumberFormat.getNumberInstance();
        JFormattedTextField distanceField = new JFormattedTextField(format);
        distanceField.setColumns(10);
        distanceField.setBackground(buttonColor);
        distanceField.setForeground(textColor);
        distanceField.setBorder(new LineBorder(borderColor, 1));
        gbc.gridx = 1;
        gbc.gridy = 0;
        frame.add(distanceField, gbc);

        JButton calculateButton = new JButton("Convert");
        calculateButton.setBackground(buttonColor);
        calculateButton.setForeground(textColor);
        calculateButton.setBorder(new LineBorder(borderColor, 1));

        gbc.gridx = 0;
        gbc.gridy = 1;
        gbc.gridwidth = 2;
        frame.add(calculateButton, gbc);

        JLabel kmLabel = new JLabel("Kilometers: ");
        kmLabel.setForeground(textColor);
        gbc.gridx = 0;
        gbc.gridy = 2;
        gbc.gridwidth = 2;
        frame.add(kmLabel, gbc);

        JLabel metersLabel = new JLabel("Meters: ");
        metersLabel.setForeground(textColor);
        gbc.gridx = 0;
        gbc.gridy = 3;
        gbc.gridwidth = 2;
        frame.add(metersLabel, gbc);

        JLabel feetLabel = new JLabel("Feet: ");
        feetLabel.setForeground(textColor);
        gbc.gridx = 0;
        gbc.gridy = 4;
        gbc.gridwidth = 2;
        frame.add(feetLabel, gbc);

        calculateButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                try {
                    double miles = ((Number)distanceField.getValue()).doubleValue();
                    double kilometers = miles * 1.60934;
                    double meters = miles * 1609.34;
                    double feet = miles * 5280;

                    kmLabel.setText(String.format("Kilometers: %.2f km", kilometers));
                    metersLabel.setText(String.format("Meters: %.2f m", meters));
                    feetLabel.setText(String.format("Feet: %.2f ft", feet));
                } catch (NumberFormatException | NullPointerException ex) {
                    kmLabel.setText("Kilometers: Please enter a valid number.");
                    metersLabel.setText("Meters: Please enter a valid number.");
                    feetLabel.setText("Feet: Please enter a valid number.");
                }
            }
        });

        frame.setVisible(true);
    }
}

```

## Flowchart Explaination 
![image](https://github.com/user-attachments/assets/69ecd53c-9349-4027-881a-cba576905bdb)

## Challenges
Using the formatted text field was different from using a plain text field. Instead of allowing for all outputs the
formatted text field allows us to take in only number values for the input, which is perfect for calculating distance.
Not too difficult to implement, and the process of changing some calculations and numbers from the previous assignment
was fairly simple to do.

## Video


https://github.com/user-attachments/assets/c6e057cf-8182-4a8b-87e0-79a5a42337be


