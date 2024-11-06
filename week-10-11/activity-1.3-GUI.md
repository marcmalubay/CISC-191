## Objective

Write a code that takes user input and performs calculations

## Pre-requisite

Review the [GUI](https://htmlpreview.github.io/?https://github.com/d-khan/java/blob/main/gui/Lecture.html) lecture before attending the lab.

## Task

Take a single user input using a JSpinner, and display a result.

__Expected input__

Take distance (in miles)

__Expected output__

Display results in km

## Code 
```java
import javax.swing.*;
import javax.swing.border.LineBorder;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class Main {
    public static void main(String[] args) {
        JFrame frame = new JFrame("Distance Converter");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(400, 300);

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

        SpinnerNumberModel model = new SpinnerNumberModel(0.0, 0.0, 100000.0, 0.1);
        JSpinner distanceSpinner = new JSpinner(model);
        distanceSpinner.setBackground(buttonColor);
        distanceSpinner.setForeground(textColor);

        gbc.gridx = 1;
        gbc.gridy = 0;
        frame.add(distanceSpinner, gbc);

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

        calculateButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                double miles = (double) distanceSpinner.getValue();
                double kilometers = miles * 1.60934;

                String numString = String.format("%,.2f", kilometers);
                kmLabel.setText("Kilometers: " + numString + " km");
            }
        });

        frame.setVisible(true);
    }
}

```
## Flowchart Explaination
![image](https://github.com/user-attachments/assets/9b5439e2-810b-438b-8bc9-36fddd165bf6)

## Challenges
The JSpinner takes in number inputs in certain increments, which allows the user to specifically pick what
type of input they want. Again, not too difficult of a concept to grasp and not very difficult to implement
into my code. This is just another interesting way to get an input from the user, and it works very
well for this problem.

## Video
https://github.com/user-attachments/assets/828baba4-dba6-41c8-a030-9581259164e8



