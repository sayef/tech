# Design Patterns        

**1. What are Design Patterns?**

Design patterns represent the best  practices used by experienced object-oriented software developers.  Design patterns are solutions to general problems that software  developers faced during software development. These solutions were  obtained by trial and error by numerous software developers over quite a  substantial period of time.

**2. Name types of Design Patterns?**

Design patterns can be classified in three categories: Creational, Structural and Behavioral patterns.

Creational Patterns – These design  patterns provide a way to create objects while hiding the creation  logic, rather than instantiating objects directly using new operator.  This gives program more flexibility in deciding which objects need to be  created for a given use case.

Structural Patterns – These design  patterns concern class and object composition. Concept of inheritance is  used to compose interfaces and define ways to compose objects to obtain  new functionalities.

Behavioral Patterns – These design patterns are specifically concerned with communication between objects.

**3. What are J2EE Patterns?**

These design patterns are specifically concerned with the presentation tier. These patterns are identified by Sun Java Center.
 What is Factory pattern?

Factory pattern is one of most used  design pattern in Java. This type of design pattern comes under  creational pattern as this pattern provides one of the best ways to  create an object.

In Factory pattern, we create object  without exposing the creation logic to the client and refer to newly  created object using a common interface.
 What is Abstract Factory pattern?

Abstract Factory patterns work around a  super-factory which creates other factories. This factory is also called  as factory of factories. This type of design pattern comes under  creational pattern as this pattern provides one of the best ways to  create an object.

In Abstract Factory pattern an interface  is responsible for creating a factory of related objects without  explicitly specifying their classes. Each generated factory can give the  objects as per the Factory pattern.
 What is Singleton pattern?

Singleton pattern is one of the simplest  design patterns in Java. This type of design pattern comes under  creational pattern as this pattern provides one of the best ways to  create an object.

This pattern involves a single class  which is responsible to create an object while making sure that only  single object gets created. This class provides a way to access its only  object which can be accessed directly without need to instantiate the  object of the class.

**4. How can you create Singleton class in java?**

It is two step process. First, make the  constructor private so that new operator cannot be used to instantiate  the class. Return an object of the object if not null otherwise create  the object and return the same via a method.

**5. What are the difference between a static class and a singleton class?**

Following are the differences between a static class and a singleton class.

A static class can not be a top level class and can not implement interfaces where a singleton class can.

All members of a static class are static but for a Singleton class it is not a requirement.

A static class get initialized when it is loaded so it can not be lazily loaded where a singleton class can be lazily loaded.

A static class object is stored in stack whereas singleton class object is stored in heap memory space.

**6. Can we create a clone of a singleton object?**

Yes.

**7. How to prevent cloning of a singleton object?**

Throw exception within the body of clone() method.
 Name some of the design patterns which are used in JDK library.

Following are some of the design patterns which are used in JDK library.

Decorator pattern is used by Wrapper classes.

Singleton pattern is used by Runtime, Calendar classes.

Factory pattern is used by Wrapper class like Integer.valueOf.

Observer pattern is used by event handling frameworks like swing, awt.

**8. What is the benefit of Factory pattern?**

Factory pattern encapsulates the  implementation details and underlying implementation can be changed  without any impact on caller api.

**9. What is Builder pattern?**

Builder pattern builds a complex object  using simple objects and using a step by step approach. This builder is  independent of other objects.

**10. What is Prototype pattern?**

Prototype pattern refers to creating  duplicate object while keeping performance in mind. This pattern  involves implementing a prototype interface which tells to create a  clone of the current object.

**11. When Prototype pattern is to be used?**

This pattern is used when creation of  object directly is costly. For example, an object is to be created after  a costly database operation. We can cache the object, returns its clone  on next request and update the database as and when needed thus  reducing database calls.

**12. What is Adapter pattern?**

Adapter pattern works as a bridge between  two incompatible interfaces. This pattern involves a single class which  is responsible to join functionalities of independent or incompatible  interfaces.

**13. Give an example of Adapter pattern.**

A real life example could be a case of  card reader which acts as an adapter between memory card and a laptop.  You plugin the memory card into card reader and card reader into the  laptop so that memory card can be read via laptop.

**14. What is Bridge pattern?**

Bridge is used when we need to decouple  an abstraction from its implementation so that the two can vary  independently. This type of design pattern comes under structural  pattern as this pattern decouples implementation class and abstract  class by providing a bridge structure between them.

This pattern involves an interface which  acts as a bridge which makes the functionality of concrete classes  independent from interface implementer classes. Both types of classes  can be altered structurally without affecting each other.

**15. What is Filter pattern?**

Filter pattern or Criteria pattern is a  design pattern that enables developers to filter a set of objects using  different criteria and chaining them in a decoupled way through logical  operations. This type of design pattern comes under structural pattern  as this pattern combines multiple criteria to obtain single criteria.

**16. What is Composite pattern?**

Composite pattern is used where we need  to treat a group of objects in similar way as a single object. Composite  pattern composes objects in term of a tree structure to represent part  as well as whole hierarchy. This type of design pattern comes under  structural pattern as this pattern creates a tree structure of group of  objects.

This pattern creates a class that  contains group of its own objects. This class provides ways to modify  its group of same objects.

**17. What is Decorator pattern?**

Decorator pattern allows a user to add  new functionality to an existing object without altering its structure.  This type of design pattern comes under structural pattern as this  pattern acts as a wrapper to existing class.

This pattern creates a decorator class  which wraps the original class and provides additional functionality  keeping class methods signature intact.

**18. What is Facade pattern?**

Facade pattern hides the complexities of  the system and provides an interface to the client using which the  client can access the system. This type of design pattern comes under  structural pattern as this pattern adds an interface to existing system  to hide its complexities.

This pattern involves a single class  which provides simplified methods required by client and delegates calls  to methods of existing system classes.

**19. What is Flyweight pattern?**

Flyweight pattern is primarily used to  reduce the number of objects created and to decrease memory footprint  and increase performance. This type of design pattern comes under  structural pattern as this pattern provides ways to decrease object  count thus improving the object structure of application.

Flyweight pattern tries to reuse already  existing similar kind objects by storing them and creates new object  when no matching object is found.

**20. What is Proxy pattern?**

In proxy pattern, a class represents functionality of another class. This type of design pattern comes under structural pattern.

In proxy pattern, we create object having original object to interface its functionality to outer world.

**21. What is Chain of Responsibility pattern?**

As the name suggests, the chain of  responsibility pattern creates a chain of receiver objects for a  request. This pattern decouples sender and receiver of a request based  on type of request. This pattern comes under behavioral patterns.

In this pattern, normally each receiver  contains reference to another receiver. If one object cannot handle the  request then it passes the same to the next receiver and so on.

**22. What is Command pattern?**

Command pattern is a data driven design  pattern and falls under behavioral pattern category. A request is  wrapped under an object as command and passed to invoker object. Invoker  object looks for the appropriate object which can handle this command  and passes the command to the corresponding object which executes the  command.

**23. What is Interpreter pattern?**

Interpreter pattern provides a way to  evaluate language grammar or expression. This type of pattern comes  under behavioral pattern. This pattern involves implementing an  expression interface which tells to interpret a particular context.

**24. Give an example where Interpreter pattern is used?**

This pattern is used in SQL parsing, symbol processing engine etc.

**25. What is Iterator pattern?**

Iterator pattern is very commonly used  design pattern in Java and .Net programming environment. This pattern is  used to get a way to access the elements of a collection object in  sequential manner without any need to know its underlying  representation. Iterator pattern falls under behavioral pattern  category.

**26. What are the entities of Service Locator pattern?**

Following are the entities of this type of design pattern.

Service – Actual Service which will process the request. Reference of such service is to be looked upon in JNDI server.

Context / Initial Context – JNDI Context carries the reference to service used for lookup purpose.

Service Locator – Service Locator is a single point of contact to get services by JNDI lookup caching the services.

Cache – Cache to store references of services to reuse them.

Client – Client is the object that invokes the services via ServiceLocator.

**27. What is Mediator pattern?**

Mediator pattern is used to reduce  communication complexity between multiple objects or classes. This  pattern provides a mediator class which normally handles all the  communications between different classes and supports easy maintenance  of the code by loose coupling. Mediator pattern falls under behavioral  pattern category.

**28. What is Memento pattern?**

Memento pattern is used to restore state  of an object to a previous state. Memento pattern falls under behavioral  pattern category.

**29. Name the actor classes used in Memento pattern.**

Memento pattern uses three actor classes.  Memento contains state of an object to be restored. Originator creates  and stores states in Memento objects and Caretaker object is responsible  to restore object state from Memento.

**30. What is Observer pattern?**

Observer pattern is used when there is  one-to-many relationship between objects such as if one object is  modified, its dependent objects are to be notified automatically.  Observer pattern falls under behavioral pattern category.

**31. Name the actor classes used in Observer pattern.**

Observer pattern uses three actor  classes. Subject, Observer and Client. Subject is an object having  methods to attach and detach observers to a client object. We have  created an abstract class Observer and a concrete class Subject that is  extending class Observer.

**32. What is state pattern?**

In State pattern a class behavior changes  based on its state. This type of design pattern comes under behavior  pattern. In State pattern, we create objects which represent various  states and a context object whose behavior varies as its state object  changes.

**33. What is Null Object pattern?**

In Null Object pattern, a null object  replaces check of NULL object instance. Instead of putting if check for a  null value, Null Object reflects a do nothing relationship. Such Null  object can also be used to provide default behaviour in case data is not  available.

In Null Object pattern, we create an  abstract class specifying various operations to be done, concrete  classes extending this class and a null object class providing do  nothing implemention of this class and will be used seemlessly where we  need to check null value.

**34. What is Strategy pattern?**

In Strategy pattern, a class behavior or  its algorithm can be changed at run time. This type of design pattern  comes under behavior pattern.

In Strategy pattern, we create objects  which represent various strategies and a context object whose behavior  varies as per its strategy object. The strategy object changes the  executing algorithm of the context object.

**35. What is Template pattern?**

In Template pattern, an abstract class  exposes defined way(s)/template(s) to execute its methods. Its  subclasses can override the method implementation as per need but the  invocation is to be in the same way as defined by an abstract class.  This pattern comes under behavior pattern category.

**36. What is Visitor pattern?**

In Visitor pattern, we use a visitor  class which changes the executing algorithm of an element class. By this  way, execution algorithm of element can vary as and when visitor  varies. This pattern comes under behavior pattern category. As per the  pattern, element object has to accept the visitor object so that visitor  object handles the operation on the element object.

**37. What is MVC pattern?**

MVC Pattern stands for Model-View-Controller Pattern. This pattern is used to separate application’s concerns.

Model – Model represents an object or JAVA POJO carrying data. It can also have logic to update controller if its data changes.

View – View represents the visualization of the data that model contains.

Controller – Controller acts on both  model and view. It controls the data flow into model object and updates  the view whenever data changes. It keeps view and model separate.

**38. What is Business Delegate pattern?**

Business Delegate Pattern is used to  decouple presentation tier and business tier. It is basically use to  reduce communication or remote lookup functionality to business tier  code in presentation tier code. In business tier we have following  entities.

Client – Presentation tier code may be JSP, servlet or UI java code.

Business Delegate – A single entry point class for client entities to provide access to Business Service methods.

LookUp Service – Lookup service object is  responsible to get relative business implementation and provide  business object access to business delegate object.

Business Service – Business Service  interface. Concrete classes implement this business service to provide  actual business implementation logic.

**39. What is Composite Entity pattern?**

Composite Entity pattern is used in EJB  persistence mechanism. A Composite entity is an EJB entity bean which  represents a graph of objects. When a composite entity is updated,  internally dependent objects beans get updated automatically as being  managed by EJB entity bean. Following are the participants in Composite  Entity Bean.

Composite Entity – It is primary entity  bean. It can be coarse grained or can contain a coarse grained object to  be used for persistence purpose.

Coarse-Grained Object – This object  contains dependent objects. It has its own life cycle and also manages  life cycle of dependent objects.

Dependent Object – Dependent object is an object which depends on coarse grained object for its persistence lifecycle.

Strategies – Strategies represents how to implement a Composite Entity.

**40. What is Data Access Object Pattern(DAO) pattern?**

Data Access Object Pattern or DAO pattern  is used to separate low level data accessing API or operations from  high level business services. Following are the participants in Data  Access Object Pattern.

Data Access Object Interface – This interface defines the standard operations to be performed on a model object(s).

Data Access Object concrete class – This  class implements above interface. This class is responsible to get data  from a data source which can be database / xml or any other storage  mechanism.

Model Object or Value Object – This object is simple POJO containing get/set methods to store data retrieved using DAO class.

**41. What is Front Controller pattern?**

The front controller design pattern is  used to provide a centralized request handling mechanism so that all  requests will be handled by a single handler. This handler can do the  authentication/ authorization/ logging or tracking of request and then  pass the requests to corresponding handlers. Following are the entities  of this type of design pattern.

Front Controller – Single handler for all kinds of requests coming to the application (either web based/ desktop based).

Dispatcher – Front Controller may use a dispatcher object which can dispatch the request to corresponding specific handler.

View – Views are the object for which the requests are made.

**42. What is Intercepting Filter pattern?**

The intercepting filter design pattern is  used when we want to do some pre-processing / post-processing with  request or response of the application. Filters are defined and applied  on the request before passing the request to actual target application.  Filters can do the authentication/ authorization/ logging or tracking of  request and then pass the requests to corresponding handlers.
 What are the entities of Intercepting Filter pattern?

**43. Following are the entities of this type of design pattern.**

Filter – Filter which will performs certain task prior or after execution of request by request handler.

Filter Chain – Filter Chain carries multiple filters and help to execute them in defined order on target.

Target – Target object is the request handler.

Filter Manager – Filter Manager manages the filters and Filter Chain.

Client – Client is the object who sends request to the Target object.

**44. What is Service Locator pattern?**

The service locator design pattern is  used when we want to locate various services using JNDI lookup.  Considering high cost of looking up JNDI for a service, Service Locator  pattern makes use of caching technique. For the first time a service is  required, Service Locator looks up in JNDI and caches the service  object. Further lookup or same service via Service Locator is done in  its cache which improves the performance of application to great extent.

**45. What is Transfer Object pattern?**

The Transfer Object pattern is used when  we want to pass data with multiple attributes in one shot from client to  server. Transfer object is also known as Value Object. Transfer Object  is a simple POJO class having getter/setter methods and is serializable  so that it can be transferred over the network. It does not have any  behavior. Server Side business class normally fetches data from the  database and fills the POJO and send it to the client or pass it by  value. For client, transfer object is read-only. Client can create its  own transfer object and pass it to server to update values in database  in one shot. Following are the entities of this type of design pattern.

Business Object – Business Service fills the Transfer Object with data.

Transfer Object – Simple POJO having methods to set/get attributes only.

Client – Client either requests or sends the Transfer Object to Business Object.