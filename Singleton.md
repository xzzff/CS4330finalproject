* The Singleton's purpose is to control object creation, limiting the number of objects to only one. Since there is only one Singleton instance, any instance fields of a Singleton will occur only once per class, just like static fields. Singletons often control access to resources, such as database connections or sockets.
* Thread-safety issue for Singletons would occur only rarely.

## Java
* The easiest implementation consists of a private constructor and a field to hold its result, and a static accessor method with a name like getInstance().
```java
// File Name: Singleton.java
public class Singleton {

   private static Singleton singleton = new Singleton( );

   /* A private Constructor prevents any other
    * class from instantiating.
    */
   private Singleton() { }

   /* Static 'instance' method */
   public static Singleton getInstance( ) {
      return singleton;
   }

   /* Other methods protected by singleton-ness */
   protected static void demoMethod( ) {
      System.out.println("demoMethod for singleton");
   }
}
```
* a classic Singleton design pattern:
```java
public class ClassicSingleton {

   private static ClassicSingleton instance = null;
   private ClassicSingleton() {
      // Exists only to defeat instantiation.
   }

   public static ClassicSingleton getInstance() {
      if(instance == null) {
         instance = new ClassicSingleton();
      }
      return instance;
   }
}
```
* There are three ways through which we can achieve thread safety.
*   1. Create the instance variable at the time of class loading.
*   2. Synchronize the getInstance() method.
*   3. Use synchronized block inside the if loop.
```java
package com.journaldev.designpatterns;

public class ASingleton{

	private static ASingleton instance= null;
	private static Object mutex= new Object();
	private ASingleton(){
	}

	public static ASingleton getInstance(){
		if(instance==null){
			synchronized (mutex){
				if(instance==null) instance= new ASingleton();
			}
		}
		return instance;
	}

}
```

## C++
* The classic lazy evaluated and correctly destroyed singleton.
```C++
class S
{
    public:
        static S& getInstance()
        {
            static S    instance;
            return instance;
        }
    private:
        S() {}
        S(S const&);              // Don't Implement.
        void operator=(S const&); // Don't implement
 };
 ```
 * Put a critical section to my Singleton method to make it thread-safe.
 * Example
 ``` C++
 MySingleton * GetInstance() //usage of critcal section makes it thread safe

{
      EnterCriticalSection();
      //other client threads, if any, now have to wait till current

      // thread leaves critical section. Forget semantics and

      // compilation for Crit Section, and treat this as pseudo-code

      if (m_pOnlyOneInstance == NULL)
      {
          m_pOnlyOneInstance = new MySingleton();
      }

      LeaveCriticalSection();

      return m_pOnlyOneInstance;
}
```
