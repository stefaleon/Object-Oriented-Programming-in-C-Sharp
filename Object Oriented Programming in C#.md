# - Object Oriented Programming in C# -
## edX - Microsoft: DEV204.2x


&nbsp;
## Classes and Interfaces

* Classes enable you to create your own custom, self-contained, and reusable types.
* Interfaces enable you to define a set of inputs and outputs that classes must implement in order to ensure compatibility with consumers of the classes.


&nbsp;
## Creating Classes and Members

* In Visual C#, a class is a programming construct that you can use to define your own custom types. When you create a class, you are effectively creating a blueprint for the type. The class defines the behaviors and characteristics, or class members, which are shared by all instances of the class. You represent these behaviors and characteristics by defining methods, fields, properties, and events within your class.

&nbsp;
## Partial Classes

* C# can also implement partial classes. Partial classes allow you to split the definition of the class across multiple source files. Then you compile your application, all of the parts are combined into a single file.

&nbsp;
## Instantiating Classes

* A class is just a blueprint for a type. To use the behaviors and characteristics that you define within a class, you need to create instances of the class. An instance of a class is called an object. To create a new instance of a class, you use the **new** keyword.

* When you instantiate a class, you are actually doing two things:
  * You are creating a new object in memory based on the class type.
  * You are creating an object reference that refers to the new object.


&nbsp;
## Type Inference

* When you create your object reference, instead of explicitly specifying the class type, you can allow the compiler to deduce the type of the object at compile time. This is known as type inference. To use type inference, you create your object reference by using the **var** keyword



&nbsp;
## Encapsulation in C# .

* Often considered the first pillar of object-oriented programming, encapsulation can be used to describe the accessibility of the members belonging to a class or struct.
* C# provides access modifiers and properties to help implement encapsulation in your classes. While some consider this accessibility configuration to be the only aspect of encapsulation, others also define encapsulation as the act of including all data and behavior required of the class, within the class definition. This definition can be stretched a bit in C# when using partial classes.


&nbsp;
## Private vs Public vs Protected vs Internal

* Access modifiers can be applied to class members to control how they can be accessed by other code in the application. This part of encapsulation by allows you to restrict access to members where it makes sense.

  * public: The type is available to code running in any assembly that references the assembly in which the class is contained.
  * internal: The type is available to any code within the same assembly, but not available to code in another assembly.
  * private: The type is only available to code within the class that contains it. You can only use the private access modifier with nested classes. This is the default value if you do not specify an access modifier.
  * protected: The type is only accessible within its class and by derived class instances.

* The tradition is to create private data fields in the class to prevent direct manipulation of the values for those fields, and expose properties to provide access to the values indirectly. The properties are known as accessors or getters and setters.



&nbsp;
## Properties

* As a part of encapsulation, you should consider using properties in your class files. Properties enable you to permit users of the class a means of getting and setting values for the private member data fields within your class. Properties accomplish while hiding implementation of verification code that you may have written inside the property. For example, you may want to validate a birthdate that has been passed in to ensure it is in the proper format or that it is in the correct range for the application's usage. Setting your member variables to private is known as a form of data hiding. Some also consider data hiding to be part of encapsulation.

* Properties also present an "interface" to your class by exposing a way to get or set the members of the class that the user can trust. In other words, if you have a property called public Birthdate(date birth), that accepts a birthdate from a user, you can implement the validation code in anyway you see fit, such as using regular expressions to validate or perhaps some custom logic to verify the date range, and then later change that validation logic without impacting the use of the property. Users still just pass in a birthdate in date format.




&nbsp;
## Constructors

* When you instantiate a class, you are actually calling a special method called a constructor. A constructor is a method in the class that has the same name as the class. Constructors do not use a return value however, not even void, and they must have the same name as the class file.

* Constructors are often used to specify initial or default values for data members within the new object.

* A constructor that takes no parameters is known as the default constructor. This constructor is called whenever someone instantiates your class without providing any arguments. If you do not include a constructor in your class, the Visual C# compiler will automatically add an empty public default constructor to your compiled class.

* In many cases, it is useful for consumers of your class to be able to specify initial values for data members when the class is instantiated. Your class can include multiple constructors with different signatures that enable consumers to provide different combinations of information when they instantiate your class. Recall method overloading.



&nbsp;
## Static Classes and Methods

* In some cases, you may want to create a class purely to encapsulate some useful functionality, rather than to represent an instance of anything. The concept of an instance is meaningless in this case. In scenarios like this, you can create a static class. A static class is a class that cannot be instantiated. To create a static class, you use the static keyword. Any members within the class must also use the static keyword.

* To call a method on a static class, you call the method on the class name itself instead of on an instance name.

* Non-static classes can include static members. This is useful when some behaviors and characteristics relate to the instance (instance members), while some behaviors and characteristics relate to the type itself (static members). Methods, fields, properties, and events can all be declared static. Static properties are often used to return data that is common to all instances, or to keep track of how many instances of a class have been created. Static methods are often used to provide utilities that relate to the type in some way, such as comparison functions.

* To declare a static member you use the static keyword before the return type of the member.

* Regardless of how many instances of your class exist, there is only ever one instance of a static member. You do not need to instantiate the class in order to use static members. You access static members through the class name rather than the instance name.






&nbsp;
## Anonymous classes

* As you might expect, an anonymous class is a class that does not have a name. Anonymous classes offer the programmer a convenient way of encapsulating read-only properties into a single object without the need to explicitly define a type first. The type name will be generated by the compiler. The type name is also not available at the source code level and the type of each property included in this anonymous class will be inferred by the compiler.

* To create an anonymous class, declare an anonymous object as an implicitly typed variable by using the var keyword and use the new keyword followed by a pair of braces to define fields and values for the class. Recall that using the var keyword will result in the compiler creating a variable using the same type as the expression that was used to initialize it. In this case, the type of the expression is whatever name the compiler happens to generate for the anonymous class.

* Once instantiated, you can access the fields in the object by using dot notation. Once created, you have the option to create other instances of the same anonymous class but with different values. The C# compiler will look at the names, types, number, and the order of the fields in the object in order to determine whether two instances of an anonymous class have the same type or not.

* There are quite a few restrictions on the contents of an anonymous class:
  * anonymous classes can contain only public fields
  * the fields must all be initialized
  * fields cannot be static
  * you cannot define any methods for them




&nbsp;
## Inheritance

* Inheritance is yet another pillar in the world of object-oriented programming. You can use inheritance as an aspect of code reuse by defining different classes that will contain common features and have a relationship to one another.

* Inheritance allows you to create a base class containing the core, shared attributes, and then each different class of employee would inherit these attributes whole extending them for their own special needs. The class that inherits from the base class is referred to as the derived class but also commonly referred to as a subclass. When using the term subclass, some also refer to the base class as a super class.

* The C# programming language does not support multiple inheritance directly. Multiple inheritance is a concept whereby multiple base classes can be inherited by a single subclass. In C#, a derived class can only have one base class.

* To inherit from base class in C#, you append your derived class name with a colon and the name of the base class.




&nbsp;
## Abstract Classes, Abstract and Virtual methods, Overrides

* Abstract classes cannot be instantiated.

* When you create an abstract class you may partially implement some of the behavior in the class, or not implement the behavior at all. An abstract class requires the subclass to implement some, or all, of the functionality.

* Once you create an abstract class, you decide which methods "must" be implemented in the sub classes and which methods "can" be implemented, or overridden, in the sub class.
Methods marked as *public virtual* "can" be overridden while methods marked as *public abstract* "must" be overriden. The equivalent methods in the sub class are marked with the *public override* modifier.

* Any method you declare in the abstract class that will contain some implementation in the abstract class, but can be overridden in the sub class, you decorate with the **virtual** keyword.

* An abstract method is decorated with the **abstract** keyword, like the class. There are specific constraints around an abstract method:
  * An abstract method cannot exist in non-abstract class
  * An abstract method is not permitted to have any implementation, including curly braces
  * An abstract method signature must end in a semi-colon
  * An abstract method MUST be implemented in any sub class. Failure to do so will generate a compiler warning in C#.



&nbsp;
## Sealed Classes

* The sealed keyword on a class restricts the inheritance feature of object oriented programming. If a class is derived from a sealed class then the compiler throws an error.





&nbsp;
## Interfaces

* An interface is a little bit like a class without an implementation. It specifies a set of characteristics and behaviors by defining signatures for methods, properties, events, and indexers, without specifying how any of these members are implemented.

* When a class implements an interface, the class provides an implementation for each member of the interface. By implementing the interface, the class is thereby guaranteeing that it will provide the functionality specified by the interface.

* Note the important distinction when using an Interface. A class "implements" an interface as opposed to "inheriting" a base class.

* You can think of an interface as a contract. By implementing a particular interface, a class guarantees to consumers that it will provide specific functionality through specific members, even though the actual implementation is not part of the contract.

* Programming convention dictates that all interface names should begin with an "I".

* Similar to a class declaration, an interface declaration can include an access modifier. You can use the following access modifiers in your interface declarations:
  * public: The interface is available to code running in any assembly.
  * internal: The interface is available to any code within the same assembly, but not available to code in another assembly. This is the default value if you do not specify an access modifier.


#### Adding Interface Members

* An interface defines the signature of members but does not include any implementation details. Interfaces can include methods, properties, events, and indexers:
  * To define a method, you specify the name of the method, the return type, and any parameters:
  ```
  int GetServingTemperature(bool includesMilk);
  ```
  * To define a property, you specify the name of the property, the type of the property, and the property accessors:
  ```
  bool IsFairTrade { get; set; }
  ```
  * To define an event, you use the event keyword, followed by the event handler delegate, followed by the name of the event:
  ```
  event EventHandler OnSoldOut;
  ```
  * To define an indexer, you specify the return type and the accessors:
  ```
  string this[int index] { get; set; }
  ```

* Interface members do not include access modifiers. The purpose of the interface is to define the members that an implementing class should expose to consumers, so that all interface members are public. Interfaces cannot include members that relate to the internal functionality of a class, such as fields, constants, operators, and constructors.

#### Implicit and Explicit Implementation

*  When you create a class that implements an interface, you can choose whether to implement the interface implicitly or explicitly. To implement an interface implicitly, you implement each interface member with a signature that matches the member definition in the interface. To implement an interface explicitly, you fully qualify each member name so that it is clear that the member belongs to a particular interface. In most cases, whether you implement an interface implicitly or explicitly is an aesthetic choice. It does not make a difference in how your class compiles. Some developers prefer explicit interface implementation because doing so can make the code easier to understand. The only scenario in which you must use explicit interface implementation is if you are implementing two interfaces that share a member name.


#### Interface Polymorphism

* As it relates to interfaces, polymorphism states that you can represent an instance of a class as an instance of any interface that the class implements. Interface polymorphism can help to increase the flexibility and modularity of your code.

* You can use an implicit cast to convert to an interface type, because you know that the class must include all the interface members.

* You must use an explicit cast to convert from an interface type to a derived class type, as the class may include members that are not defined in the interface.

* In many cases, you will want to create classes that implement more than one interface. For example, you might want to:
  * Implement the IDisposable interface to enable the .NET runtime to dispose of your class correctly.
  * Implement the IComparable interface to enable collection classes to sort instances of your class.
  * Implement your own custom interface to define the functionality of your class.

* To implement multiple interfaces, you add a comma-separated list of the interfaces that you want to implement to your class declaration. Your class must implement every member of every interface you add to your class declaration. 
