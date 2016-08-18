
|    |     Abstract Factory Pattern        |
|----------|:-------------:|
| What is it? |  The abstract factory pattern allows a calling component to create a group of related objects. The pattern hides the details of which classes are used to create the objects and the reason why they were selected from the calling component. This pattern is similar to the factory method patterns which presents the calling component with a set of objects. |
| What are the benefits? |   The calling component doesn’t know which classes are used to create the objects or why they were selected, which makes it possible to change the classes that are used without needing to change the components that consume them.  |
| When should you use this pattern? | Use this pattern when you need to ensure that multiple compatible objects are used by a calling component without the component needing to know which objects are able to work together. |
| When should you avoid this pattern? | Do not use this pattern to create a single object; the factory method pattern is a simpler alternative that should be used instead. |
| How do you know when you have implemented the pattern correctly? | This pattern is implemented correctly when a calling component receives a set of objects without knowing which classes were used to instantiate them. The calling component should be able to access the object’s functionality only through the protocols they implement or the base classes from which they are derived. |
| Are there any common pitfalls? | The main pitfall is to leak details of the classes that are used to the calling component, either creating a dependency on the decisionmaking process that selects classes or creating a dependency on specific classes. |
| Are there any related patterns? | The factory method pattern is a simpler pattern when only a single object is required. The abstract factory method is often combined with the singleton and prototype patterns (see the “Variations on the Abstract Factory Pattern” section). |

|    |     Builder Pattern        |
|----------|:-------------:|
| What is it? |  The builder pattern puts the logic and default configuration values required to create an object into a builder class. This allows calling components to create objects with minimal configuration data and without needing to know the default values that will be used to create the object. |
| What are the benefits? |   This pattern makes it easier to change the default configuration values used to create an object and to change the class from which instances are created.  |
| When should you use this pattern? | Use this pattern when a complex configuration process is required to create an object and you don’t want the default configuration values to be disseminated throughout the application. |
| When should you avoid this pattern? | Don’t use this pattern when every data value required to create an object will be different for each instance. |
| How do you know when you have implemented the pattern correctly? | The calling component can create objects by providing just the data values for which there are no default values (although values may also be provided to override some or all of the defaults). |
| Are there any common pitfalls? | No. |
| Are there any related patterns? | This pattern can be combined with the factory method or abstract factory patterns to change the implementation class used to create the object based on the configuration data provided by the calling component. |

|    |     Prototype Pattern        |
|----------|:-------------:|
| What is it? |  The prototype pattern creates new objects by copying an existing object, known as the prototype. |
| What are the benefits? |    The main benefit is to hide the code that creates objects from the components that use them; this means that components don’t need to know which class or struct is required to create a new object, don’t need to know the details of initializers, and don’t need to change when subclasses are created and instantiated. This pattern can also be used to avoid repeating expensive initialization each time a new object of a specific type is created.   |
| When should you use this pattern? | This pattern is useful when you are writing a component that needs to create new instances of objects without creating a dependency on the class initializer. |
| When should you avoid this pattern? | There are no drawbacks to using this pattern, but you should understand the other patterns to ensure that you pick the most suitable for your application. |
| How do you know when you have implemented the pattern correctly? | To test for an effective implementation of this pattern, change the initializer for the class or struct used for the prototype object and check to see whether a corresponding change is required in the component that creates clones. As a second test, create a subclass of the prototype’s class and ensure that the component can clone it without requiring any changes. |
| Are there any common pitfalls? | The main pitfall is selecting the wrong style of copying when cloning the prototype object. There are two kinds of copying available—shallow and deep—and it is important to select the correct kind for your application. |
| Are there any related patterns? | The most closely related pattern is the object template pattern. Also see the singleton pattern, which provides a means by which a single object can be shared to avoid needing to create additional instances. |

|    |     Singleton Pattern        |
|----------|:-------------:|
| What is it? |  The singleton pattern ensures that only one object of a given type exists in the application. |
| What are the benefits? |    The singleton pattern can be used to manage objects that represent real-world resources or to encapsulate a shared resource.   |
| When should you use this pattern? | The singleton pattern should be used when creating further objects doesn’t increase the number of real-world resources available or when you want to consolidate an activity such as logging. |
| When should you avoid this pattern? | The singleton pattern isn’t useful if there are not multiple components that require access to a shared resource or if there are no objects that represent real-world resources in the application. |
| How do you know when you have implemented the pattern correctly? | The pattern has been correctly implemented when there is only one instance of a given type and when that instance cannot be copied and cloned and when further instances cannot be created. |
| Are there any common pitfalls? | The main pitfalls are using reference types (which can be copied) or classes that implement the NSCopying protocol (which can be cloned). The singleton pattern usually requires some protections against concurrent use, which is a common source of problems. |
| Are there any related patterns? | The object pool pattern, which manages a fixed number of objects rather than the single object handled by the singleton pattern. |

|    |     Factory Method Pattern        |
|----------|:-------------:|
| What is it? |  The factory method pattern selects an implementation class to satisfy a calling component’s request without requiring the component to know anything about the implementation classes or the way they relate to one another. |
| What are the benefits? |   This pattern consolidates the logic that decides which implementation class is selected and prevents it from being diffused throughout the application. This also means that calling components rely only on the top-level protocol or base class and do not need any knowledge about the implementation classes or the process by which they are selected.  |
| When should you use this pattern? | Use this pattern when you have several classes that implement a common protocol or that are derived from the same base class. |
| When should you avoid this pattern? | Do not use this pattern when there is no common protocol or shared base class because this pattern works by having the calling component rely on only a single type. |
| How do you know when you have implemented the pattern correctly? | This pattern is implemented correctly when the appropriate class is instantiated without the calling component knowing which class was used or how it was selected. |
| Are there any common pitfalls? | No. The factory method pattern is simple to implement. |
| Are there any related patterns? | The factory method pattern is often combined with the singleton and object pool patterns. |

|    |     Object Pool Pattern        |
|----------|:-------------:|
| What is it? |  The object pool pattern manages a collection of reusable objects that are provided to calling components. A component obtains an object from the pool, uses it to perform work, and returns it to the pool so that it can be allocated to satisfy future requests. An object that has been allocated to a caller is not available for use by other components until it has been returned to the pool. |
| What are the benefits? |    The object pool pattern hides the construction of objects from the components that use them and allows expensive initializations to be amortized through reusing objects repeatedly.   |
| When should you use this pattern? | Use the object pool pattern when you have a number of identical objects whose creation you need to manage, either because the objects represent real-world resources or because creating new instances is expensive. |
| When should you avoid this pattern? | Do not use this pattern if there can be only one object in existence at any moment (use the singleton pattern instead) or if there are no limits on the number of objects that can exist (allow calling components to create their own instances or use one of the other patterns, such as the factory method pattern) |
| How do you know when you have implemented the pattern correctly? | The pattern is implemented correctly when objects are allocated to calling components without the need to create new instances and when an object returned to the pool is used to satisfy a subsequent request. |
| Are there any common pitfalls? | The main pitfall is the implementation of concurrency protections that ensure that objects are allocated correctly and without corrupting the data structures used to implement the pattern. |
| Are there any related patterns? | The singleton pattern shares some common ideas with the object pool pattern but manages a single object. |

|    |     Object Pool Variations        |
|----------|:-------------:|
| What are they? |  The variations on the object pool pattern allow you to change the way that the object pool works to operate in different situations. |
| What are the benefits? |    These variations change the behavior of the pool so that it can service calling components with different expectations and needs and manage objects with a range of characteristics and life cycles.   |
| When should you use these variations? | You should use these variations when the basic implementation of the pattern does not meet your needs. |
| When should you avoid these variations? | These variations require advanced concurrency techniques and should be avoided unless you can test them thoroughly and have a solid understanding of Cocoa concurrency. |
| How do you know when you have implemented the variations correctly? | The only way to be sure you have implemented these variations correctly is through thorough testing. |
| Are there any common pitfalls? | These are advanced techniques, and it is easy to misuse concurrency protections to create a pool that doesn’t work or that performs poorly. |
| Are there any related patterns? | Not applicable. |

|    |     Object Template Pattern        |
|----------|:-------------:|
| What is it? |  The object template pattern uses a class or struct as the specification for the data types and logic for a given data type. Objects are created using the template, and values for the data are set during initialization, either through the use of default values in the template or using values provided by the component to the class or struct initializer, also known as the constructor. |
| What are the benefits? |    The object template pattern provides the foundation for grouping data values and the logic that manipulates them together, known as encapsulation. Encapsulation allows an object to present an API to its consumers while hiding the private implementation of that API. This helps prevent the tight coupling of components.   |
| When should you use this pattern? | You should use this pattern in all but the simplest of projects. Swift tuples are an interesting feature, but they can present a long-term maintenance problem, and only a little extra work is required to create a simple class or struct instead. |
| When should you avoid this pattern? | In general, there are no drawbacks in using this pattern, but there are many advanced techniques to this pattern |
| How do you know when you have implemented the pattern correctly? | The pattern is implemented correctly when you can make changes to the private implementation of a class or struct without making corresponding changes to the components that use it. |
| Are there any common pitfalls? | The only pitfall with this pattern is using a struct as a template when you intended to use a class. Structs and classes have a lot in common, but they behave differently when objects created from them are assigned to new variables. |
| Are there any related patterns? | The prototype pattern provides an alternative technique for creating objects. |
