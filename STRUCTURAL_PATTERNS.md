
|    |     Adapter Pattern        |
|----------|:-------------:|
| What is it? |  The adapter pattern allows two components with incompatible APIs to work together by introducing an adapter that maps from one component to the other. |
| What are the benefits? |   This pattern allows you to integrate components for which you cannot modify the source code into your application. This is a common problem when you use a third-party framework or when you are consuming the output from another project.  |
| When should you use this pattern? | Use this pattern when you need to integrate a component that provides similar functionality to other components in the application but that uses an incompatible API to do so. |
| When should you avoid this pattern? | Do not use this pattern when you are able to modify the source code of the component that you want to integrate or when it is possible to migrate the data provided by the component directly into your application. |
| How do you know when you have implemented the pattern correctly? | The pattern is implemented correctly when the adapter allows the component to be integrated into the application without requiring modification of the application or the component. |
| Are there any common pitfalls? | The only pitfall is trying to extend the pattern to force integration of a component that does not provide the functionality intended by the API for which it is being adapted. |
| Are there any related patterns? | Many of the structural patterns have similar implementations but different intents. Ensure that you select the correct pattern! |

|    |     Bridge Pattern        |
|----------|:-------------:|
| What is it? |  The bridge pattern separates an abstraction from its implementation so that either can be changed without a corresponding change in the other. More commonly, the bridge pattern is used to resolve a problem known as an exploding class hierarchy, which usually arises through repeated but poorly thought-out refactoring and requires an ever-increasing number of classes to add new features to the application. |
| What are the benefits? |   When the bridge pattern is applied to the exploding class hierarchy problem, the benefit is that adding a new feature to the application requires only a single class. More broadly, the pattern isolates the impact of a change when an abstraction or its implementation changes.  |
| When should you use this pattern? | Use this pattern to resolve the exploding class hierarchy problem or to bridge between one API and another. |
| When should you avoid this pattern? | Do not use this pattern when attempting to integrate third-party components; use the adapter pattern instead. |
| How do you know when you have implemented the pattern correctly? | In the case of the exploding class hierarchy problem, the pattern is correctly implemented when adding a new feature or when support for a new platform can be done with a single class. More broadly, the pattern is implemented correctly when you can change an abstraction (such as a protocol or a closure signature) without having to make a corresponding change in its implementation. |
| Are there any common pitfalls? | The exploding class hierarchy will not be resolved if the common code is not separated from the platform-specific code. |
| Are there any related patterns? | Many of the structural patterns have similar implementations but different intents. Ensure that you select the correct pattern! |

|    |     Composite Pattern        |
|----------|:-------------:|
| What is it? |  The composite pattern allows a tree of individual objects and collections of objects to be treated consistently. |
| What are the benefits? |   The consistency that the composite pattern brings means that components that operate on the tree structure are simpler and do not need to have knowledge of the different objects types that are in use.  |
| When should you use this pattern? | Use this pattern when you have a tree structure that contains leaf nodes and collections of objects. |
| When should you avoid this pattern? | This pattern is applicable only to tree data structures.  |
| How do you know when you have implemented the pattern correctly? | The pattern is implemented correctly when components that use the tree structure can treat all of the objects it contains using the same type or protocol. |
| Are there any common pitfalls? | This pattern is best suited to tree structures that are not modified once they have been created. Adding support for modifying the tree undermines the benefit of the pattern. |
| Are there any related patterns? | Many of the structural patterns have similar implementations but different intents. Ensure that you select the correct pattern! |

|    |     Decorator Pattern        |
|----------|:-------------:|
| What is it? |  The decorator pattern allows the behavior of individual objects to be changed without requiring changes to the classes that are used to create them or the components that consume them. |
| What are the benefits? |   The changes in behavior defined with the decorator pattern can be combined to create complex effects without needing to create large numbers of subclasses.  |
| When should you use this pattern? | Use this pattern when you need to change the behavior of objects without changing the class they are created from or the components that use them. |
| When should you avoid this pattern? | Do not use this pattern when you are able to change the class that creates the objects you want to modify. It is usually simpler and easier to modify the class directly. |
| How do you know when you have implemented the pattern correctly? | The pattern has been implemented correctly when you can select some of the objects created from a class to be modified without affecting all of them and without requiring changes to the class. |
| Are there any common pitfalls? | The main pitfall is implementing the pattern so that it affects all of the objects created from a given class rather than allowing changes to be applied selectively. A less common pitfall is implementing the pattern so that it has hidden side effects that are not related to the original purpose of the objects being modified. |
| Are there any related patterns? | Many of the structural patterns have similar implementations but different intents. Ensure that you select the correct pattern! |

|    |     Flyweight Pattern        |
|----------|:-------------:|
| What is it? |  The flyweight pattern shares common data objects between multiple calling components. |
| What are the benefits? |   The flyweight pattern reduces the amount of memory needed to create the data objects required by the calling components and the amount of work required to create them. The impact of implementing the pattern increases with the number of calling components that share the data.  |
| When should you use this pattern? | Use this pattern when you are able to identify and isolate sets of identical data objects that are used by calling components. |
| When should you avoid this pattern? | Do not use this pattern if there is no shared data or if the number of shared data objects is small and easy to create.  |
| How do you know when you have implemented the pattern correctly? | The pattern has been implemented correctly when all of the calling components rely on the same set of immutable shared data objects (known as the extrinsic data) and have their own individual state data (known as the intrinsic data). The calling components should be able to concurrently modify the intrinsic data safely and not be able to modify the extrinsic data at all. |
| Are there any common pitfalls? | The common pitfalls include inadvertently creating more than one set of extrinsic data objects, not protecting against concurrent operations on the intrinsic data, allowing the extrinsic data to be modified, and over-optimizing the creation of extrinsic objects. |
| Are there any related patterns? | Many of the structural patterns have similar implementations but different intents. Ensure that you select the correct pattern! |

|    |     Proxy Pattern        |
|----------|:-------------:|
| What is it? |  The proxy pattern defines an object—the proxy—that represents some other resource, such as another object or a remote service. Calling components operate on the proxy, which in turn operates on the underlying resource. |
| What are the benefits? |   Proxies allow close control over the way that the underlying resource is accessed, which is useful when you need to intercept and adapt operations.  |
| When should you use this pattern? | Proxies are used in three main situations: to define an interface to a remote resource such as a web page or RESTful service, to manage the execution of expensive operations, and to restrict access to the methods and properties of other objects. |
| When should you avoid this pattern? |  Do not use this pattern when the problem falls outside of the three situations (Remote Objects, Expensive Operations, and Reference Counting). Instead, use one of the other structural patterns.   |
| How do you know when you have implemented the pattern correctly? | The pattern is implemented correctly when the proxy object can be used to perform operations on the resource it represents. |
| Are there any common pitfalls? | The only pitfall is allowing instances of the underlying class to be instantiated when a proxy is used to restrict access to an object. |
| Are there any related patterns? | Many of the structural patterns have similar implementations but different intents. Ensure that you select the correct pattern! |

|    |     Facade Pattern        |
|----------|:-------------:|
| What is it? |  The façade pattern simplifies the use of complex APIs to perform common tasks. |
| What are the benefits? |   The complexity required to use an API is consolidated into a single class, which minimizes the impact of changes in the API and simplifies the components that consume the API functionality.  |
| When should you use this pattern? | Use the façade pattern when you are working with classes that need to be used together but that don’t have compatible APIs. |
| When should you avoid this pattern? | Do not use the façade pattern when integrating single components into the application; use the adapter pattern instead.  |
| How do you know when you have implemented the pattern correctly? | The façade pattern is implemented when common tasks can be performed without calling components having any dependency on the underlying objects or their supporting data types. |
| Are there any common pitfalls? | The pitfall when implementing the façade pattern is to leak details of the underlying objects. This means that the calling components are still dependent on the underlying classes or supporting types and will require modification when they change. |
| Are there any related patterns? | Many of the structural patterns have similar implementations but different intents. Ensure that you select the correct pattern! |
