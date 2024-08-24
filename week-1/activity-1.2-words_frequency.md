# Lab: Words frequencies

## Objectives
Count number of words

## Pre-requisite
Review of the week 1 Java contents

## Tasks
Define a method named getWordFrequency that takes an array of strings, the size of the array, and a search word as parameters. 
Method getWordFrequency() then returns the number of occurrences of the search word in the array parameter (case insensitive). 
Then, write a main program that reads a list of words into an array, calls method getWordFrequency() repeatedly, and outputs the words 
in the arrays with their frequencies. Assume that the list will always contain less than 20 words.

The program must define and call a method:
```public static int getWordFrequency(String[] wordsList, int listSize, String currWord)```

## Example input
hey Hi Mark hi mark

## Example output
hey 1  
Hi 2    
Mark 2   
hi 2   
mark 2   
