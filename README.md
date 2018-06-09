# Design-Patterns
All Design Patterns code and explanation are here, explanation will be inside each folder of specific Design Pattern and the code will be written in C# at environment Visual Studio Code.

Trying to make the code simple as I can with good explanation, read inside the folder the explanation of the design pattern, clone the design pattern to your environment and run it to see the results and understand it even deeply.

# Adapter

In computer programming, the adapter pattern (often referred to as the wrapper pattern or simply a wrapper) is a design pattern that translates 
one interface for a class into a compatible interface. An adapter allows classes to work together that normally could not because of incompatible 
interfaces, by providing its interface to clients while using the original interface. The adapter translates calls to its interface into calls to the original 
interface, and the amount of code necessary to do this is typically small. The adapter is also responsible for transforming data into appropriate forms.
 For instance, if multiple boolean values are stored as a single integer but your consumer requires a 'true'/'false', the adapter would be responsible for 
extracting the appropriate values from the integer value.

It allows two unrelated interfaces to work together through the different objects, possibly playing same role.
It modifies original interface.

# Bridge

At first sight, the Bridge pattern looks a lot like the Adapter pattern in that a class is used to convert one kind of interface to another. 
However, the intent of the Adapter pattern is to make one or more classes' interfaces look the same as that of a particular class. 
The Bridge pattern is designed to separate a class's interface from its implementation so you can vary or replace the implementation without 
changing the client code.


Bridge pattern:

It is a structural pattern
Abstraction and implementation are not bound at compile time
Abstraction and implementation - both can vary without impact in client
Uses composition over inheritance.
Use the Bridge pattern when:

You want run-time binding of the implementation,
You have a proliferation of classes resulting from a coupled interface and numerous implementations,
You want to share an implementation among multiple objects,
You need to map orthogonal class hierarchies.


Before Bridge Pattern:

                   ----Shape---
                  /            \
         Rectangle              Circle
        /         \            /      \
BlueRectangle  RedRectangle BlueCircle RedCircle

After Bridge Pattern:

# Builder
# Chain of Responsibility
# Command
# Composite
# Decorator
# Facade
# Factory
# Flyweight
# Interpreter 
# Mediator 
# Memento 
# Observer
# Prototype
# Proxy
# Singleton
# State
# Strategy
# Template Method
# Visitor 