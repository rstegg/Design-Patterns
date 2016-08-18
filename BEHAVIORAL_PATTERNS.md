|    |     Chain of Responsibility Pattern        |
|----------|:-------------:|
| What is it? |  The chain of responsibility pattern organizes sequentially a set of objects that may be able to take responsibility for a request from a calling component. The sequence of objects is referred to as a chain, and each object in the chain is asked to take responsibility for the request. The request moves along the chain until one of the objects takes responsibility or the end of the chain is reached. |
| What are the benefits? |   The chain of responsibility allows objects that can process requests to be ordered into a preferential sequence that can be reordered, extended, or reduced without any impact on the calling component, which has no insight into the objects that comprise the chain.  |
| When should you use this pattern? | Use this pattern when there are several objects that can handle a request, only one of which should be used. |
| When should you avoid this pattern? |  Do not use this pattern when there is only one object that can handle a request or when the calling component needs to select the object.   |
| How do you know when you have implemented the pattern correctly? | The pattern is implemented correctly when the set of objects that can take responsibility for a request are arranged sequentially and each is offered the chance to take responsibility in turn. The individual objects in the chain have no knowledge of one another (other than the next link in the chain) |
| Are there any common pitfalls? | The pitfall is leaking details of the objects in the chain, either to one another or to the calling component. |
| Are there any related patterns? | The chain of responsibility pattern shares some common concepts with the command pattern. |

|    |     Command Pattern        |
|----------|:-------------:|
| What is it? |  The command pattern is used to encapsulate details of how to invoke a method on an object in a way that allows the method to be invoked at a different time or by a different component. |
| What are the benefits? |   There are lots of situations in which using a command is useful, but the most common ones are supporting undo operations and creating macros.  |
| When should you use this pattern? | Use this pattern when you want to allow methods to be invoked by components that otherwise have no information about the object that will be used, the method that will be invoked, or the arguments that will be provided. |
| When should you avoid this pattern? |  Do not use this pattern for regular method invocation. |
| How do you know when you have implemented the pattern correctly? | The pattern is implemented correctly when a component can use a command to invoke a method on an object without needing details of that object or the method itself. |
| Are there any common pitfalls? | The main pitfall is to require the component that executes the command to have knowledge of the method or object that will be used. |
| Are there any related patterns? | The memento pattern provides a model by which snapshots of an object’s entire state can be used instead of individual operations. |

|    |     Mediator Pattern        |
|----------|:-------------:|
| What is it? |  The mediator pattern simplifies peer-to-peer communication between objects by introducing a mediator object that acts as a communications broker between the objects. |
| What are the benefits? |   Instead of having to keep track of and communicate with of all of its peers individually, an object just deals with the mediator.  |
| When should you use this pattern? | Use this pattern when you are dealing with a group of objects that need to communicate freely between one another. |
| When should you avoid this pattern? |  Don’t use this pattern if you have one object that needs to send notifications to a range of disparate objects; use the observer pattern instead. |
| How do you know when you have implemented the pattern correctly? | The mediator pattern is implemented correctly when each object deals only with the mediator and has no direct knowledge of its peers. |
| Are there any common pitfalls? | It is important that the mediator not provide peers with access to one another so that they might become interdependent. |
| Are there any related patterns? | This pattern is closely related to—and often combined with—the observer pattern. |

|    |     Memento Pattern        |
|----------|:-------------:|
| What is it? |  The memento pattern captures the complete state of an object into a memento that can be used to reset the object at a later date. |
| What are the benefits? |   The memento pattern allows a complete reset of an object without the need to track and apply individual undo commands.  |
| When should you use this pattern? | Use this pattern when there is a “known-good” point in an object’s life that you may want to return to at some point in the future. |
| When should you avoid this pattern? |  This pattern should be used only when you need to return an object to an earlier state. Use the command pattern if you need to add support for undoing the effect of only the most recent operation. |
| How do you know when you have implemented the pattern correctly? | The pattern is implemented correctly if the object can be returned to an earlier state from any starting position. |
| Are there any common pitfalls? | The most common pitfall is to not completely capture or set the state. |
| Are there any related patterns? | The memento and command patterns share a common philosophy. |

|    |     Observer Pattern        |
|----------|:-------------:|
| What is it? |  The observer pattern allows one object to register to receive notifications about changes in another object without needing to depend on the implementation of that object. |
| What are the benefits? |   This pattern simplifies application design by allowing objects that provide notifications to do so in a uniform way without needing to know how those notifications are processed and acted on by the recipients.  |
| When should you use this pattern? | Use this pattern whenever one object needs to receive notifications about changes in another object but where the sender of the notifications does not depend on the recipient to complete its work. |
| When should you avoid this pattern? |  Do not use this pattern unless the sender of the notifications is functionally dependent from the recipients, such that the recipients could be removed from the application without preventing the sender from performing its work. |
| How do you know when you have implemented the pattern correctly? | The observer pattern is implemented correctly when an object can receive notifications without being tightly coupled to the object that sends them. |
| Are there any common pitfalls? | The biggest pitfall with this pattern is allowing the objects that send and receive notifications to become interdependent. |
| Are there any related patterns? | No. |

|    |     Strategy Pattern        |
|----------|:-------------:|
| What is it? |  The strategy pattern is used to create classes that can be extended without modification, through the application of algorithm objects that conform to a well-defined protocol. |
| What are the benefits? |   The strategy pattern allows third-party developers to change the behavior of classes without modifying them and can allow low-cost changes to be made in projects that have expensive and lengthy validation procedures for specific classes.  |
| When should you use this pattern? | Use this pattern when you need classes that can be extended without being modified. |
| When should you avoid this pattern? |  There is no reason to avoid this pattern. |
| How do you know when you have implemented the pattern correctly? | The strategy pattern is implemented correctly when you can extend the behavior of a class by defining and applying a new strategy without needing to make any changes to the class itself. |
| Are there any common pitfalls? | No. The strategy pattern is simple to implement. |
| Are there any related patterns? | The strategy and visitor patterns are often used together. |

|    |     Visitor Pattern        |
|----------|:-------------:|
| What is it? |  The visitor pattern allows new algorithms to operate on collections of heterogeneous objects without needing to modify or subclass the collection class. |
| What are the benefits? |   The visitor pattern is useful when you want to provide collection classes as part of frameworks without requiring third-party developers to modify the source code. This pattern is also useful in projects where modifying core classes triggers expensive testing procedures.  |
| When should you use this pattern? | Use this pattern when you have classes that manage collections of mismatched objects and you want to perform operations on them. |
| When should you avoid this pattern? |  There is no need to use this pattern when all of the objects are of the same type or when the collection class can be readily modified. |
| How do you know when you have implemented the pattern correctly? | The pattern is implemented correctly when a visitor class can extend the behavior of the collection class by defining methods that handle each type of object in the collection. |
| Are there any common pitfalls? | The only pitfall is trying to avoid using the double dispatch technique, which I describe in the “Understanding Double Dispatch” sidebar. |
| Are there any related patterns? | The visitor pattern is another way to conform to the open/closed principle supported by the strategy pattern. |

|    |     Template Method Pattern        |
|----------|:-------------:|
| What is it? |  The template method pattern allows specific steps in an algorithm to be replaced by implementations provided by a third-party, either by specifying functions as closures or by creating a subclass. |
| What are the benefits? |   This pattern is useful when you are writing frameworks that you want to allow other developers to extend and customize.  |
| When should you use this pattern? | Use this pattern to selectively permit steps in any algorithm to be changed without modifying the original class. |
| When should you avoid this pattern? |  Do not use this pattern if the entire algorithm can be changed. See the other patterns for alternatives.  |
| How do you know when you have implemented the pattern correctly? | This pattern is implemented correctly when selected steps in an algorithm can be changed without modifying the class that defines the algorithm. |
| Are there any common pitfalls? | No. |
| Are there any related patterns? | This pattern has similar goals to the strategy and visitor patterns. |
