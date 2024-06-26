# Java_Individual_Work_2_12.06

* Develop a simple book management application with ArrayList.
* User should be able to add a book to ArrayList.
* User should be able to remove a book from ArrayList.

## Easy: Work with String in ArrayList. All the actions should be available for user.
```java
import java.util.ArrayList;
import java.util.Scanner;

public class Main {
    public static void main (String[] args) { 
      ArrayList<String> bookStore = new ArrayList<String>();

      var scanner = new Scanner(System.in);
      System.out.println("Please enter a book you want to add to the store: ");
      var bookAdded = scanner.nextLine();
      addBook(bookStore, bookAdded);


      System.out.println("Please enter a book you want to remove from the store: ");
      var bookRemoved = scanner.nextLine();
      removeBook(bookStore, bookRemoved);


      scanner.close();
    }

    public static void addBook(ArrayList<String> bookStore, String book){
      bookStore.add(book);
      System.out.println(book + " has been added to the bookstore");
    }

    public static void removeBook(ArrayList<String> bookStore, String book){
      bookStore.removeIf(b -> b.equals(book));
      System.out.println(book + " has been removed from the bookstore");
    }

}
```
## Medium: Work with String User should be able to repeat all the actions infinitely.
```java
import java.util.ArrayList;
import java.util.Scanner;

public class Main {
    public static void main (String[] args) { 
      ArrayList<String> bookStore = new ArrayList<String>();
      Scanner scanner = new Scanner(System.in);

      while(true){
      
        while(true){
          System.out.println("Please enter a book you want to add to the store or type 'exit' to stop: ");
          String bookAdded = scanner.nextLine();
        
          if(bookAdded.equalsIgnoreCase("exit")){
             break;
          }
        
          addBook(bookStore, bookAdded);
        }
      
        printArrayList(bookStore);

        while(true){
          System.out.println("Please enter a book you want to remove from the store or type 'done' to stop: ");
          String bookRemoved = scanner.nextLine();

          if(bookRemoved.equalsIgnoreCase("done")){
            break;
          }
        
          removeBook(bookStore, bookRemoved);
          printArrayList(bookStore);
        }
      }
    }

    public static void printArrayList(ArrayList<String> books){
        System.out.println("Bookstore has the following books: ");
        for (String book : books){
          System.out.println(book);
        }
    }

    public static void addBook(ArrayList<String> bookStore, String book){
        bookStore.add(book);
        System.out.println(book + " has been added to the bookstore");
    }

    public static void removeBook(ArrayList<String> bookStore, String book){
        bookStore.removeIf(b -> b.equals(book));
        System.out.println(book + " has been removed from the bookstore");
    }

}
```
