Mixins
------

### mixin classes ###
Mixins are essentailly an abstract class relying on either abstract methods, an abstract base class, an interface, or a signature.

Note: In C++ they may consist of an class inheriting from a base class with pure virtual methods.
```
 mixin AMixin {
   abstract f()
   g() : void { ... f() ... }
 }
 
 class A mixin AMixin {
   virtual f() { ... }
   h() { ... g() ... }
 }
```
Here f() is not essentail to being a mixin, but defines the use of a mixin rather than just a class.

The class keyword is optional
```
 mixin class AMixin {
   abstract f()
   g() : void { ... f() ... }
 }
```
### mixin methods ###
declaring a mixin method via a type anchor
```
  mixin method (signature aSignature)::aMethod(...):string { ... }
```
#### overloading of mixin methods ####
```
  mixin method (subclass of aClass)::aMethod(...):string { ... }
```
### Syntax ###

### Semantics ###
A Mixin is actually a class that inherits from **Super**, provides some method(s) used by **Super**, and may rely on abstract methods provided by **Super**. **Super** is an implicit parameter passed through to inherited classes.
```
 class AnotherMixin : Super {
   ...
 }
```

note this is illustrative as there is no domain restriction on **Super** here. There is an implicit signature requirement to the mixins super class created by the mixin. As a result this may only work in dynamic and prototypical versions of the language.
