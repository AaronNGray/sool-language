# Classes

## Introduction
Classes are simular to C++'es classes except they can be mapped in a multitude of different ways. Although vtables can be used, for efficiency reasons methods are generally mapped as arrays of pointers to methods that are based on the first declaing class in the heirachy; this mechanism is simular to Eiffel's. Also SOOL classes are much richer in functionality and include for example virtual nested classes allowing a higher level of stucturing of code object relationships through inheritance.

The following is an example basic point class. Note the use of the **self** reference rather than **this** pointer. **self** is not required normally but is used here to avoid name clashes with simularly named arguments. The **instantiate** keyword which is shown later in this chapter makes instantiation much easier with less code needed. Note unlike C++ that members are public by default.

```
 class point {
 protected:
   var x:integer
   var y:integer
 public:
   constructor point(x:integer, y:integer) {
     self.x = x
     self.y = y
   }
 }
```
## members

### member types and sections
```
 public:
 protected:
 private:
 prohibited:
```
```
 constructors:
 destructors:
 methods:
 messages:
 interrupts:
 static:
 functions:
 operators:
```
```
 public
 protected
 private
 prohibited
```
```
 constructor
 destructor
 method
 message
 interrupt
 static
 function
 operator
```
```
 public {
   ...
 }
 protected {
   ...
 }
 private {
   ...
 }
 prohibited {
   ...
 }
```
```
 constructors {
   ...
 }
 destructors {
   ...
 }
 methods {
   ...
 }
 messages {
   ...
 }
 interrupts {
   ...
 }
 static {
   ...
 }
 functions {
   ...
 }
 operators {
   ...
 }
```
#### special member and section types

```
 runtime:
   ...
 compiletime:
    ...
```
```
 runtime {
   ...
 }
 compiletime {
   ...
 }
```

### constructors

Constructors maybe named differently than the class they are constructing, but must be qualified in usage by the class name.

The keyword **constructor** is used rather than in C++ using the class name as the class name actually can polute the classes method name space, for example if the class is the class 'set' then the class would not be able to have a 'set()' method method.

#### default constructor

An implicit default constructor will be defined if there are no other constructors which returns an object with the default values for all its members if there are any members, unless of cause the class is abstract.

`  constructor () {}`

#### explicit constuctors

Constructors are exlicit by default and have to be explicitly called unless they are declared implicit.
```
 class int {
   explicit constructor (long)
     ....
 }
```
you may use the implicit or explicit keyword in the definition of the constructor.

#### implicit constructors

Implicit constructors may be automatically used in type conversions and parameter conversions.

```
 class long {
   implicit constructor (int)
 }
```

#### named constructors

A named constructor maybe used rather than an explicit constructor.

```
 class int {
   constructor long(long)
 }
```


#### disallowed constructors

Disallowing a constructor

`  no constructor bogus ();`

Disallowing the default constructor

`  no constructor ();`

This is often done in C++ by making a constructor private, not implementing it and commenting that it should not be implemented. Or in C++11 you can use `= delete` which is just weird.

`  final no constructor ();`

Means that inheriting classes cannot create a default constructor.

#### instatiating constructors
```
 class cartesian {
   constructor (x = 0, y = 0) instantiate
 protected:
   real x
   real y
 }
```
#### constructor example
```
 class cartesian {
   constructor (x = 0, y = 0) instantiate
   constructor polar(angle a, real radius)
   implicit constructor polar(polar p)
 protected:
   real x
   real y
 }
  
 class polar {
   constructor (angle a, real radius) instatiate
   constructor cartesian(real x, real y)
   implicit constructor cartesian(cartesian c)
 protected:
   angle a
   real radius
 }
```
#### destructors

Automated 'taredown' for non library classes or arena memory managed objects maybe employed, either on a destructor, class, or module level.

#### static and non static constructors

static constructors are like C++ constructors.

otherwise constructors are callable from a domain and are like "methods" of that domain.

#### public, protected, and private constructors

constructors may have visibility constraints.

#### class constructors and destructors
class constructors and destructors are called on the initialization and deinitilization of the module they are exist within.

```
 class X {
   ...
   class constructor () {
     ...
   }
   class destructor () {
     ...
   }
   ...
 }
```
or

```
 class Y {
   ...
   class {
     constructor () {
       ...
     }
     destructor () {
       ...
     }
   }
   ...
 }
```
### conversions
```
 class cartesian (
   constructor polar(polar p);
   implicit converter (polar p) = polar(p);
   ...
 };
 
 polar p( 90, 1.0);
 cartesian c = p;
```
implicit and explicit conversions. Conversion are explicit by default.

### casts

casts actually convert the type of a variable or expression and keep the same binary value. As they are dangerious and only allowed in systems programmming by importing the System.Platform module and having the correct security permissions.

### instance variables

Instance variables are common to all objects of a certain class.

#### initializers

Instance variables may have default initializers otherwise they will be initialized to the types default initializer value.
```
 class X {
   var i : integer = 5
   var s : string = "Hello there !!!\n"
   ...
 }
```
more complex initializers maybe used such as initializer lists and templating of initialized values too.

### slots

Slots are dynamic and like pythons or selfs slots, they can be declared dynamically for dynamic classes or prottype objects.

### new and delete

Simular to C++'es new and delete operators. And may be overriden and specialized or adapted simularly too.

### methods

## virtual members

**virtual** members can be overriden by inheriting classes.

## final members

**final** members may not be overriden in inheriting classes or subclassses.

implicit members and types
--------------------------

## self

**self** is a reference to the containing object.

`  self.aVariable`

allows access to members

self may also allow access to members when hidden in scope by a parameter :-
```
 class A {
   method m( a : Int) {
     self.a = a
   }
   var a : Int
 }
```
Sub objects may also be accessed as an associative array which fits in with the dynamic and prototypical versions of the language, but will also work with meta information / reflection in static implementations.

`  self["aVariable"]`

## Self

**Self** is the type of **self**. Which is short hand for **type of self**.

`  type Self = type of self`

or

`  Self = like self`

The following gives access to all the protected methods in a class as an associative array :-

`  Self[protected method]`

**Self** is an anchor
```
 class cons(X : any) {
   var val : X
   var next : ref Self
 }
```
## super

**super** is a reference to a classes primary inheriting class.

Note: This is essentailly the same as Java.

## Super

**Super** provides a class with the type/class of its primary inheriting class (from the **extends** clause, or first inherited class), or **Bottom** or **Void** if there is no super class. This is used in the construction of mixins.

## parent

**parent[]** is an array of parent classes. **parent[0]** is equal to **super**.

## Parent

**Parent[]** is an array of parent class types. **Parent[0]** is equal to **Super**.

## outer

**outer** is the parent scopes object. This works for nested class and types.

## Outer

**outer** is the parent scopes object type. This works for nested class and types.

## this

**this**, **pointer** and **unit.address** are only defined if the "Platform.System" package is included.

It is defined in terms of 'self' as follows :-

`  this : pointer to Self = self.address`

`  this : This = self.address`

## This

**This** is the type of **this**.

`  type This = pointer to Self`

## abstract classes

Abstract classes cannot be instatiated directly but can be inherited by other non abstract classes.
```
 abstract class A {
   ...
 }
```
## anonymous classes

### anonymous inner classes
```
 interface Listener {
   public void event(Event e)
 }
 
 button.addListener(
   new Listener {
     public void event(Event e) {
       ...
     }
   }
 )
```

## nested classes ##

Classes maybe nested inside other classes.
```
 class C {
   private class D {
     ...
   }
 ...
 }
```

They may also have a visibility modifier as above.

## virtual classes ##
```
 class C {
   virtual class V {
     ...
   }
 }
```
here class D inherits from class C and extends the virtual class C::V with D's V :-

```
 class D : C {
   extend virtual class V {
     ...
   }
 }
```

here class E inherits from class C and overrides the virtual class C::V with E's V :-

```
 class E : C {
   override virtual class V {
     ...
   }
 }
```

here class F::V will be flagged as an error :-
```
 class F : C {
   virtual class V {
     ...
   }
 }
```

## Singleton classes ##
Singleton or Static classes.

```
 singleton class ASingletonClass {
   ...
 } ASingleton
```

## Extended classes ##
Simular to C\#'s extended classes.

```
 import X
 
 extend class X.X {
   ...
 }
```
## First class classes ##
```
 class a = class {
   ...
 }
```
```
 type b(X, Y) = class inherit X {
   y:Y
 }
```
## Generic classes ##
Generic classes allow parametric polymorphism. They are discussed under Generacism.


## Templated classes

Templated classes are discussed under Templates.

### OOF and Microsoft COM Object Models

#### OOF

The Object Oriened Framework is the underlying unifying language support framework that allows static, dynamic, and prototypical languages to be implemented.

#### COM

```
 import COM
 
 class aClass : COM.Class( CLSID="...") {
   interface anInterface : COM.Interface( IID="...") {
     method aMethod():void
   }
   interface anotherInterface : COM.Interface( IID="...") {
     method aMethod():void
   }
 }
```

COM can also be done as an extension class to an existing OOF class.

## Syntax
```
 ClassDeclaration:
   ClassHead "{" ClassBody "}"
```
### Non Generic and no Signatures
```
 ClassHead:
   ["abstract"] "class" ClassName ["by ref" | "by value"] [("shared" | "repeated")["only"]] ["extends" ClassName] [(":" | "inherit") ["shared" | "repeated"] ClassName ("," ["shared" | "repeated"] ClassName)*] ["implements" InterfaceName ("," InterfaceName)*]
```
### Generic and with Signatures
```
 ClassHead:
   ["abstract"] "class" ClassName ["by ref" | "by value"] [("shared" | "repeated")["only"]] ["signature" SignatureDefinition] ["extends" TypeDefinition] [(":" | "inherit") ["shared" | "repeated"] TypeDefinition ("," ["shared" | "repeated"] TypeDefinition)*] ["implements" (SignatureDefinition|InterfaceDefinition) ("," (SignatureDefinition|InterfaceDefinition))*]
```
## Semantics
