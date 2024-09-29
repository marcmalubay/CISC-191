# Overriding methods

## Objective
Understand how to use overriding methods.

## Pre-requisite
Review the "Inheritance" lecture before attending the lab. 

## Task
- Write main() and a base `Book` class, define a derived class called `Encyclopedia` with member methods to get and set private fields of the following types:

  - String to store the edition
  - int to store the number of pages

  Within the derived `Encyclopedia` class, define a printInfo() method that overrides the `Book` class' printInfo() method by printing the title, author, publisher, publication date, edition, and number of pages.

## Expected input
```
The Hobbit
J. R. R. Tolkien
George Allen & Unwin
21 September 1937
The Illustrated Encyclopedia of the Universe
Ian Ridpath
Watson-Guptill
2001
2nd
384
```
## Expected output
```Course Information:
CBook Information: 
   Book Title: The Hobbit
   Author: J. R. R. Tolkien
   Publisher: George Allen & Unwin
   Publication Date: 21 September 1937
Book Information: 
   Book Title: The Illustrated Encyclopedia of the Universe
   Author: Ian Ridpath
   Publisher: Watson-Guptill
   Publication Date: 2001
   Edition: 2nd
   Number of Pages: 384
```

## Code

## Book class
```java
public class Book {
    protected String title;
    protected String author;
    protected String publisher;
    protected String publication;

   public void setTitle(String n) {
      title = n;
   }

    public void setAuthor(String n) {
      author = n;
   }
   
    public void setPublisher(String n) {
      publisher = n;
   }
    
    public void setPublication(String n) {
      publication = n;
   }
   public void printInfo() {
      System.out.println("CBook Information:");
      System.out.println("  Book Title: "  + title);
      System.out.println("  Author: "  + author);
      System.out.println("  Publisher: "  + publisher);
      System.out.println("  Publication Date: "  + publication);
   }
}
```

## Encyclopedia Class
```java
public class Encyclopedia extends Book {
    private String edition;
    private int pages;

    public void setEdition(String n) {
        edition = n;
    }
    
    public void setPages(int n) {
        pages = n;
    }

@Override
    public void printInfo() {
        System.out.println("Book Information:");
        System.out.println("  Book Title: "  + title);
        System.out.println("  Author: "  + author);
        System.out.println("  Publisher: "  + publisher);
        System.out.println("  Publication Date: "  + publication);
        System.out.println("  Edition: "  + edition);
        System.out.println("  Pages: "  + pages);
   }
}
```

## Main class
```java
public class Main {
    public static void main(String[] args) {
        Book book = new Book();
        Encyclopedia encyclopedia = new Encyclopedia();

        book.setTitle("The Hobbit");
        book.setAuthor("J. R. R. Tolkien");
        book.setPublisher("George Allen & Unwin");
        book.setPublication("21 September 1937");
        book.printInfo();
        
        encyclopedia.setTitle("The Illustrated Encyclopedia of the Universe");
        encyclopedia.setAuthor("Ian Ridpath");
        encyclopedia.setPublisher("Watson-Guptill");
        encyclopedia.setPublication("2001");
        encyclopedia.setEdition("2nd");
        encyclopedia.setPages(384);
        encyclopedia.printInfo();
   }
}
```

