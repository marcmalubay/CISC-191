
```java
import java.util.Scanner;
import java.io.FileInputStream;
import java.io.IOException;

public class MyClass {
   public static void main (String[] args) throws IOException {
      FileInputStream fileByteStream = null; 
      Scanner inFS = null;                  
      String file;                   
       
      System.out.println("Opening file ParkPhotos.txt.");
      fileByteStream = new FileInputStream("ParkPhotos.txt");
      inFS = new Scanner(fileByteStream);

      while (inFS.hasNextLine()) {
         file = inFS.nextLine();
         String newFile = file.replaceAll("_photo.jpg", "_info.txt");
         System.out.println(newFile);
      }
      
      System.out.println("Closing file ParkPhotos.txt.");
      fileByteStream.close(); 
   }
}
```
