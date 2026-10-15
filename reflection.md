Structs vs Classes
This assignment helped me understand how object-oriented programming works behind the scenes. In Python, creating a class is straightforward because the language automatically manages methods, object creation, and the self parameter. In C, I had to manually create a struct to store data and add function pointers to simulate methods. I also had to explicitly pass the object pointer (self) whenever calling a function. Another manual step was assigning the correct function pointers during initialization so that objects knew which functions to use.

Based on this assignment, when a method is called on an object in Python, something similar is happening internally. The object contains references to methods, and Python automatically passes the object as the self parameter. In C, I had to perform these steps myself by storing function pointers in the struct and calling them explicitly. This gave me a much better understanding of how classes and methods are implemented at a lower level and how higher-level languages simplify the process for programmers.


Inheritance Implementation
Inheritance was implemented in C using composition by embedding the Character struct as the first member of the Warrior and Mage structs. This allowed the derived structs to reuse the data and behavior of the base Character type. Because the base struct was stored first, a pointer to a derived object could be cast to a Character pointer and used similarly to the parent type.

This approach is different from Python, where inheritance is built into the language. In Python, inheritance can be created simply by writing class Warrior(Character):. Python automatically provides access to the parent class's attributes and methods. The Python approach is easier to read, requires less code, and reduces the chance of programming errors. In contrast, the C approach requires manual setup and careful management of memory and function pointers.


Understanding OOP Mechanics
Function pointers enable polymorphism because different objects can store different function addresses for the same method. In this assignment, both Warrior and Mage used an attack method, but each object's function pointer referenced a different implementation. As a result, calling attack on a Character pointer could produce different behaviors depending on the actual object type. This is the foundation of polymorphism.

Systems programmers may use these patterns because they provide many of the benefits of object-oriented programming while still using C. Function pointers and embedded structs allow code reuse, flexibility, and abstraction without requiring built-in OOP support. Understanding these techniques also helps explain how languages such as Python and C++ implement objects and method dispatch internally. This assignment showed me that many high-level OOP features are ultimately built on lower-level concepts that can be recreated manually in C.