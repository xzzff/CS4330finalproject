
## Java classes
* A class is nothing but a blueprint or a template for creating different objects which defines its properties and behaviors. Java class objects exhibit the properties and behaviors defined by its class. A class can contain fields and methods to describe the behavior of an object.
* Every class has a constructor. Each time a new object is created, at least one constructor will be invoked.
* A class can have more than one constructor.
* There is no direct equivalent of a destructor in java.
* For classes that need to explicitly tidy up, the convention is to define a close method and use finalize only for sanity checking


## C++ classes
* A class in C++ is a user defined type or data structure declared with keyword class that has data and functions (also called methods) as its members whose access is governed by the three access specifiers private, protected or public (by default access to members of a class is private).
* A C++ constructor will have exact same name as the class and it does not have any return type at all, not even void. Constructors can be very useful for setting initial values for certain member variables.
#include <iostream>
using namespace std;
class Line {
   public:
      void setLength( double len );
      double getLength( void );
      Line();  // This is the constructor
   private:
      double length;
};
