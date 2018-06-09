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

The key difference between a builder and factory IMHO, is that a builder is useful when you need to do lots of things to build an object. 
For example imagine a DOM. You have to create plenty of nodes and attributes to get your final object. 
A factory is used when the factory can easily create the entire object within one method call.

One example of using a builder is a building an XML document, I've used this model when building HTML fragments for example I might have a 
Builder for building a specific type of table and it might have the following methods (parameters are not shown):

BuildOrderHeaderRow()
BuildLineItemSubHeaderRow()
BuildOrderRow()
BuildLineItemSubRow()

# Chain of Responsibility

With this pattern, you create a chain of objects that examine a request. 
Each in turn examines the request and either handles it or passes it to the next object in the chain.

Benefits

- decouples the sender of the request and its receivers
- simplifies the object because it doesn have to know the chain structure and keep references to its members
- allows the dynamic adding or removal of responsibility by changing the order or members of the chain


Drawbacks

- execution of the request isn't garanteed, it may fall off the chain if no object handles it
- runtime characteristics can be hard to observe and debug


Potential Use cases

- mouse clicks and keyboard events.
- email. For example, email is received and passed to the first handler, the spam handler. It is then either processed or passed to the second handler, etc.

-------------------------------------------------------------

- the chain contains multiple instances, and each of them performs a different action
- each instance in the chain can choose to propagate to the next instance, or stop the flow

So, with servlet filters, you can have

- a filter that checks if the user is authenticated. If he is, the filter propagates to the next filter

- the next filter checks if the user has permissions to the current resource. If it does, it propagate to the next

- the next logs the current request URL and the username, and always propagate to the next

- there is nothing else in the chain, so the target object is finally invoked

# Command

The main motivation for using the Command pattern is that the executor of the command does not need to know anything at all about what 
the command is, what context information it needs on or what it does. All of that is encapsulated in the command.

This allows you to do things such as have a list of commands that are executed in order, that are dependent on other items, 
that are assigned to some triggering event etc.

Let us focus on the non-implementation aspect of the command design, and some main reasons for using the 
Command desing pattern grouped in two major categories:

- Hiding actual implementation of how the command is executed
- Allow methods to be built around command, aka command extensions

# Composite

Use the Composite pattern when

- you want to represent part-whole hierarchies of objects.
- you want clients to be able to ignore the difference between compositions of objects and individual objects. 
Clients will treat all objects in the composite structure uniformly.



# Decorator

The Decorator Pattern is used for adding additional functionality to a particular object as opposed to a class of objects. It is easy to add 
functionality to an entire class of objects by subclassing an object, but it is impossible to extend a single object this way. 
With the Decorator Pattern, you can add functionality to a single object and leave others like it unmodified.

# Facade

The Facade design pattern simplifies the interface to a complex system; 
because it is usually composed of all the classes which make up the subsystems of the complex system.

A Facade shields the user from the complex details of the system and provides them with a simplified view of it which is easy to use. 
It also decouples the code that uses the system from the details of the subsystems, making it easier to modify the system later.

# Factory

So, to me the factory pattern is like a hiring agency. You've got someone that will need a variable number of workers. 
This person may know some info they need in the people they hire, but that's it.

So, when they need a new employee, they call the hiring agency and tell them what they need. 
Now, to actually hire someone, you need to know a lot of stuff - benefits, eligibility verification, etc. 
But the person hiring doesn't need to know any of this - the hiring agency handles all of that.

In the same way, using a Factory allows the consumer to create new objects without having to know the details of how they're created, 
or what their dependencies are - they only have to give the information they actually want.

( Creates objects without exposing the instantiation logic to the client. )

# Flyweight

Flyweight pattern try to reuse already existing similar kind objects by storing them and creates new object when no matching object is found.

First of all they belong to different categories: Prototype is creational one, Flyweight is structural one.

In Prototype objects' creation go through cloning, it ease object's creation. By making a request for cloning we create new cloned object each time.

In Flyweight by making a request we try to reuse as much objects as possible by sharing them. New required object will be created if we don't find such one. 
It's being done for resource optimization.

While in Prototype we could clone even one object, Flyweight pattern makes sense to use when in the application we use big number of objects.

General information:

Using static fields, there can only ever be one instance of the object in use at any one point in time. 
Using the flyweight pattern, you can have any number of different instances in use simultaneously, (each one of which is used multiple times). 
The canonical example of the flyweight pattern is for a text editor, where you need an object instantiated for each and every character in the document. 
Instead of having one object in memory for each character in a 10,000 word document, you then only need 26 objects, 
(assuming document only uses lower case letters), one for the letter 'a', one for the letter 'b', etc., 
and they are reused, transiently, over and over again throughout the document, 
each time you need to perform some function or action requiring an 'a' object.


# Interpreter 

Given a language, define a representation for its grammar along with an interpreter that uses the representation to interpret sentences in the language.


What problems can the Interpreter design pattern solve?

- A grammar for a simple language should be defined
- So that sentences in the language can be interpreted.

When a problem occurs very often, it could be considered to represent it as a sentence in a simple language (Domain Specific Languages) 
so that an interpreter can solve the problem by interpreting the sentence.

For example, when many different or complex search expressions must be specified. Implementing (hard-wiring) them directly 
into a class is inflexible because it commits the class to particular expressions and makes it impossible to specify new expressions or 
change existing ones independently from (without having to change) the class.

# Mediator 

The Observer pattern works well when no coordination between the observers is necessary and the observes relationship goes one way.

For example, let objects B and C observe object A. 
When object A fires event X, then object B should execute method Y() and object C should execute method Z(). If methods B.Y() and C.Z() 
are totally independent and require no coordination, then go ahead and use the observer pattern.

On the other hand, if B.Y() must be executed before C.Z() then you will want to use the Mediator pattern where the mediator encapsulates 
this coordination. In this scenario, mediator M would observe object A and would have references to objects B and C. 
When A fires event X, M will handle the event and call B.Y() and C.Z() in the prescribed order.

Also, if objects A, B and C need to observe each other then using a mediator as an intermediary will go a long way to decouple these objects and 
avoid spaghetti code.



# Memento 

The memento class is the one holding the different states you are dealing with in your object - it is what enables the "undo/redo" functionality.

What problems can the Memento design pattern solve? 

- The internal state of an object should be saved externally so that the object can be restored to this state later.
- The object's encapsulation must not be violated.

The problem is that a well designed object is encapsulated so that its representation (data structure) is hidden inside the object and 
can't be accessed from outside the object.


What solution does the Memento design pattern describe?


Make an object (originator) itself responsible for

- saving its internal state to a (memento) object and
- restoring to a previous state from a (memento) object.


Only the originator that created a memento is allowed to access it.

A client (caretaker) can request a memento from the originator (to save the internal state of the originator) and pass a memento back to 
the originator (to restore to a previous state).

This enables to save and restore the internal state of an originator without violating its encapsulation.

# Observer

Define a one-to-many dependency between objects where a state change in one object results in all its dependents being notified and updated automatically.

ou have a concrete example of a Student and a MessageBoard. 
The Student registers by adding itself to the list of Observers that want to be notified when a new Message is posted to the MessageBoard. 
When a Message is added to the MessageBoard, it iterates over its list of Observers and notifies them that the event occurred.

Think Twitter. When you say you want to follow someone, Twitter adds you to their follower list. When they sent a new tweet in, 
you see it in your input. In that case, your Twitter account is the Observer and the person you're following is the Observable.

# Prototype
# Proxy
# Singleton
# State
# Strategy
# Template Method
# Visitor 