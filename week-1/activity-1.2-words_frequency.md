# Lab: Words frequencies

## Objectives
Count number of words

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

## Code 
```java
public class Main {
    public static int getWordFrequency(String[] wordsList, int listSize, String currWord) {
        int frequency = 0;

        for (int i = 0; i <= listSize - 1; i++) {
            String lower = wordsList[i].toLowerCase();

            if (currWord.toLowerCase().equals(lower)) {
                frequency += 1;
            }
        }
        return(frequency);
    }

    public static void main(String[] args) {
        String[] words = {"hey", "Hi", "Mark", "hi", "mark"};
        int listSize = words.length;

        for (int i = 0; i <= listSize - 1; i++) {
            int freq = getWordFrequency(words, listSize, words[i]);
            System.out.println(words[i] + " " + freq);
        }
    }
}
```
