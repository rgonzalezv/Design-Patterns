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
                  /                  \
         Rectangle                    Circle
        /         \                  /      \
	BlueRectangle  RedRectangle BlueCircle RedCircle


After Bridge Pattern:

             ----Shape---                        Color
            /            \                       /   \
	Rectangle(Color)   Circle(Color)           Blue   Red

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

The Prototype pattern is a creation pattern based on cloning a pre-configured object. 
The idea is that you pick an object that is configured for either the default or in the ballpark of some specific use case and then you 
clone this object and configure to your exact needs.

The pattern is useful to remove a bunch of boilerplate code, when the configuration required would be onerous. 
I think of Prototypes as a preset object, where you save a bunch of state as a new starting point.

# Proxy

A proxy, in its most general form, is a class functioning as an interface to something else. 
The proxy could interface to anything: a network connection, a large object in memory, 
a file, or some other resource that is expensive or impossible to duplicate. 

In short, a proxy is a wrapper or agent object that is being called by the client to access the real serving object behind the scenes. 
Use of the proxy can simply be forwarding to the real object, or can provide additional logic. In the proxy, extra functionality can be provided, 
for example caching when operations on the real object are resource intensive, 
or checking preconditions before operations on the real object are invoked. For the client, usage of a proxy object is similar to using the real object, 
because both implement the same interface.

What problems can the Proxy design pattern solve?

- The access to an object should be controlled.
- Additional functionality should be provided when accessing an object.

When accessing sensitive objects, for example, it should be possible to check that clients have the needed access rights.

What solution does the Proxy design pattern describe?

Define a separate Proxy object that

- can be used as substitute for another object (Subject) and
- implements additional functionality to control the access to this subject.

This enables to work through a Proxy object to perform additional functionality when accessing a subject. For example, to check the access rights of clients accessing a sensitive object.
To act as substitute for a s

# Singleton

Ensure a class has only one instance, and provide a global point of access to it.

# State

This pattern is used in computer programming to encapsulate varying behavior for the same object based on its internal state. 
This can be a cleaner way for an object to change its behavior at runtime without resorting to large monolithic conditional statements 
and thus improve maintainability.

What problems can the State design pattern solve?

- An object should change its behavior when its internal state changes.
- State-specific behavior should be defined independently. That is, new states should be added and the behavior of existing states should be changed independently.
Implementing state-specific behavior directly within a class is inflexible because it commits the class to a particular behavior and makes it impossible to add a new state or change the behavior of an existing state later independently from (without changing) the class.


What solution does the State design pattern describe?

- Define separate (state) objects that encapsulate state-specific behavior for each state. That is, define an interface (State) for performing state-specific behavior, and define classes that implement the interface for each state.
- A class delegates state-specific behavior to its current state object instead of implementing state-specific behavior directly.

This makes a class independent of how state-specific behavior is implemented. New states can be added by defining new state classes.
A class can change its behavior at run-time by changing its current state object.

# Strategy

Define a family of algorithms, encapsulate each one, and make them interchangeable. 
Strategy lets the algorithm vary independently from clients that use it.

What is a Strategy? A strategy is a plan of action designed to achieve a specific goal;

“Define a family of algorithms, encapsulate each one, and make them interchangeable. 
Strategy lets the algorithm vary independently from clients that use it.” (Gang of Four);
Specifies a set of classes, each representing a potential behaviour. Switching between those classes changes the application behaviour. (the Strategy);

This behaviour can be selected at runtime (using polymorphism) or design time;

Capture the abstraction in an interface, bury implementation details in derived classes;

# Template Method

Similarities

Strategy and Template method patterns have a lot of similarities between them. 
Both Strategy and Template method patterns can be used for satisfying the Open-Closed Principle 
and making the software module easy to extend without changing its code. Both patterns represent separation of generic functionality 
from the detailed implementation of that functionality. However, they differ a little in terms of granularity they offer.


Differences
Here are some of the differences I have observed while studying these two patterns:

- In Strategy, the coupling between the client and strategy is more loose whereas in Template Method, the two modules are more tightly coupled.

- In Strategy, mostly an interface is used though abstract class can also be used depending on the situation, and concrete class is not used whereas in 
Template method mostly abstract class or concrete class is used, interface is not used.

- In Strategy pattern, generally entire behaviour of the class is represented in terms of an interface, 
on the other hand, Template method is used for reducing code duplication and the boilerplate code is defined in base framework or abstract class. 
In Template Method, there can even be a concrete class with default implementation.

- In simple words, you can change the entire strategy (algorithm) in Strategy pattern, however, in Template method, 
only some things change (parts of algorithm) and rest of the things remain unchanged. In Template Method, the invariant steps are implemented in 
an abstract base class, while the variant steps are either given a default implementation, or no implementation at all. In Template method, 
the component designer mandates the required steps of an algorithm, and the ordering of the steps, but allows the component client to extend or 
replace some number of these steps.

# Visitor 


What problems can the Visitor design pattern solve?

- It should be possible to define a new operation for (some) classes of an object structure without changing the classes.

When new operations are needed frequently and the object structure consists of many unrelated classes, it's inflexible to add new subclasses each time a new operation is required because "[..] distributing all these operations across the various node classes leads to a system that's hard to understand, maintain, and change." [1]


What solution does the Visitor design pattern describe?


- Define a separate (visitor) object that implements an operation to be performed on elements of an object structure.
- Clients traverse the object structure and call a dispatching operation accept(visitor) on an element — that "dispatches" (delegates) 
the request to the "accepted visitor object". The visitor object then performs the operation on the element ("visits the element").

This makes it possible to create new operations independently from the classes of an object structure by adding new visitor objects.