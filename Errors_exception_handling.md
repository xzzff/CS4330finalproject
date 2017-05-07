
* Errors and exception can occur at runtime as well as at compile-time.va

## Java
* Memory error, hardware error, JVM error etc.
* DivideByZero exception, NullPointerException, ArithmeticException, ArrayIndexOutOfBoundsException, etc.

* Java provides specific keywords for exception handling purposes, we will look after them first and then we will write a simple program showing how to use them for exception handling.

* throw – We know that if any exception occurs, an exception object is getting created and then Java runtime starts processing to handle them. Sometime we might want to generate exception explicitly in our code, for example in a user authentication program we should throw exception to client if the password is null. throw keyword is used to throw exception to the runtime to handle it.

* throws – When we are throwing any exception in a method and not handling it, then we need to use throws keyword in method signature to let caller program know the exceptions that might be thrown by the method. The caller method might handle these exceptions or propagate it to it’s caller method using throws keyword. We can provide multiple exceptions in the throws clause and it can be used with main() method also.

   import java.io.*;
   public class className {

   public void deposit(double amount) throws RemoteException {
    // Method implementation
     throw new RemoteException();
   }
   // Remainder of class definition
   }

* try-catch – We use try-catch block for exception handling in our code. try is the start of the block and catch is at the end of try block to handle the exceptions. We can have multiple catch blocks with a try and try-catch block can be nested also. catch block requires a parameter that should be of type Exception.
* Example:
   import java.io.FileReader;
   import java.io.IOException;

   public class Try_withDemo {

   public static void main(String args[]) {
     try(FileReader fr = new FileReader("E://file.txt")) {
     char [] a = new char[50];
     fr.read(a);   // reads the contentto the array
     for(char c : a)
     System.out.print(c);   // prints the characters one by one
    }catch(IOException e) {
     e.printStackTrace();
     }
   }
   }

* finally – finally block is optional and can be used only with try-catch block. Since exception halts the process of execution, we might have some resources open that will not get closed, so we can use finally block. finally block gets executed always, whether exception occurred or not.
* Example:
   public class ExcepTest {

   public static void main(String args[]) {
     int a[] = new int[2];
     try {
     System.out.println("Access element three :" + a[3]);
     }catch(ArrayIndexOutOfBoundsException e) {
     System.out.println("Exception thrown  :" + e);
     }finally {
     a[0] = 6;
     System.out.println("First element value: " + a[0]);
     System.out.println("The finally statement is executed");
     }
   }
   }

## C++


