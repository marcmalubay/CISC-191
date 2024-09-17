
```java
import java.util.Scanner;
import java.io.FileInputStream;
import java.io.IOException;

public class MyClass {
   public static void main (String[] args) throws IOException {
      FileInputStream fileByteStream = null; // File input stream
      Scanner inFS = null;                   // Scanner object
      String file;                       // Data value from file
       
      // Try to open file
      System.out.println("Opening file ParkPhotos.txt.");
      fileByteStream = new FileInputStream("ParkPhotos.txt");
      inFS = new Scanner(fileByteStream);
      
      // File is open and valid if we got this far 
      // (otherwise exception thrown
      
      while (inFS.hasNextLine()) {
         file = inFS.nextLine();
         String newFile = file.replaceAll("_photo.jpg", "_info.txt");
         System.out.println(newFile);
      }
      
      // Done with file, so try to close it
      System.out.println("Closing file ParkPhotos.txt.");
      // close() may throw IOException if fails
      fileByteStream.close(); 
   }
}
```
