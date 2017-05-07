## Java
* Built-in garbage collection.
* Java Memory Model(JVM).
* JVM memory is divided into separate parts. At broad level, JVM Heap memory is physically divided into two parts – Young Generation and Old Generation.
* Young generation is the place where all the new objects are created. When young generation is filled, garbage collection is performed. This garbage collection is called Minor GC. Young Generation is divided into three parts – Eden Memory and two Survivor Memory spaces.
* Old Generation memory contains the objects that are long lived and survived after many rounds of Minor GC. Usually garbage collection is performed in Old Generation memory when it’s full. Old Generation Garbage Collection is called Major GC and usually takes longer time.
* An object becomes eligible for Garbage collection or GC if it is not reachable from any live threads or by any static references.

## C++
* In C++, the only way to organize memory management on a larger scale than the class is by overloading the global operator new.
extern void* operator new(size_t, class Heap&);
* A smart pointer type is defined as any class type that overloads operator->, operator*, or operator->*.
* New and Delete operators allocate memory for objects from a pool called the free store.
* The new operator calls the special function operator new, and the delete operator calls the special function operator delete.

#include <iostream>
#include <cstring>
using namespace std;

int main()
{
    int num;
    cout << "Enter total number of students: ";
    cin >> num;
    float* ptr;
    
    // memory allocation of num number of floats
    ptr = new float[num];

    cout << "Enter GPA of students." << endl;
    for (int i = 0; i < num; ++i)
    {
        cout << "Student" << i + 1 << ": ";
        cin >> *(ptr + i);
    }

    cout << "\nDisplaying GPA of students." << endl;
    for (int i = 0; i < num; ++i) {
        cout << "Student" << i + 1 << " :" << *(ptr + i) << endl;
    }

    // ptr memory is released
    delete [] ptr;

    return 0;
}
