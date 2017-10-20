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
