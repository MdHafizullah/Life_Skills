# SOLID Principles

Basically, **SOLID** is a short form of the design principles of Object Oriented Programming.  
It was developed by **Robert C. Martin**.  
It is developed because it helps to **easily maintain and add new features** and make code simple.  

---

## Why we need SOLID?
- Simple and maintainable  
- Scalability  
- Testing and debugging  

---

## 1. Single Responsibility Principle (SRP)

One class should do only one work.  
If a class does more than one work, then it becomes very hard to maintain and understand.  
In this program we have two classes but both fulfill different responsibilities.  

### Example of SRP
```java
class First {
    public void print() {
         System.out.println("Something");
    }
}

class Second {
    public void printHere(First first) {
         System.out.println("Something Else Here");
    }
}

public class Hafiz {
      public static void main(String[] args) {
      
          First first = new First();
          first.print();
          
          Second second = new Second();
          second.printHere(first);
      }
}

2. Open/Closed Principle (OCP)

When we add new feature in code then it should be open for extension.
But when we modify existing code then it should be closed for modification.
Suppose any feature is added in code then old code should not be deleted.

Example of OCP

interface First {
      double mul();
}

class Second implements First {
      double num1, num2;
      
      Second(double num1, double num2) {
             this.num1 = num1;
             this.num2 = num2;
      }
      
      public double mul() {
           return num1 * num2;
      }
}

class Third implements First {
      double num3;
      
      Third(double num3) {
             this.num3 = num3;
      }
      
      public double mul() {
           return num3;
      }
}

public class Hafiz {
      public static void main(String[] args) {
      
            First s = new Second(5, 5);   // reference of interface with object of Second
            First t = new Third(10);      // reference of interface with object of Third  
            
            System.out.println("Multiple of two element: " + s.mul());
            System.out.println("Here single element print: " + t.mul());
      }
}

Note: We make two classes and one interface. In the interface, there is one method mul() and that interface is implemented in both classes.
If anything is added, then create a new class.

3. Liskov Substitution Principle (LSP)

Suppose we make two classes: one is a superclass and second is a subclass.
If we use the subclass in place of superclass, then the program should execute correctly (no error).
If the subclass does not follow the rule of the superclass, then LSP is violated.

4. Interface Segregation Principle (ISP)

Suppose we make an interface and also make a class.
If this interface has many methods, then we should not forcefully implement all methods in the class.

Advantages of ISP

No unnecessary implementation
Better code
Loose coupling
High cohesion
Reusability

5. Dependency Inversion Principle (DIP)

Basically, high-level modules should not depend on low-level modules.
Both should depend on abstraction.

Why DIP is important?

Loose coupling
Extensibility
Testability
Maintainability

