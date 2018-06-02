# Inheritance

Inheritance can be applied to classes, signatures, interfaces, records, variants, datatypes, modules, and packages.

## single inheritance

Primary inheritance, or extension.

```
   class A extends B {
       ...
   }
```

This is used a mechanism to work with .Net and JVM environments. And also effects v table layout if using v table implementation.

## mixin inheritance

```
   mixin M uses signature S {
       ...
   }
   
   class A implements signature S mixin M {
       ...
   }
```
## delegation
deletation using **as** allows another class or object's interface to be added to a class as if it was inherited publically.
```
  class A {
      ...
      as B {
          return b
      }
      as C = c
      ...
      var b : B
      var c : ref C
      ...
  }
```
## multiple inheritance

### The diamond problem

The diamond problem in multiple inheritance brings up the ideas of shared and repeated inheritance.

note: diagram needed

### Shared and Repeated inheritance ###

When class A inherits from classes B and C and they inheritfrom a class D. They may either inherit there own copy of class D, this is repeated or structural inheritance or may inherit a common copy of class D, this is shared or virtual (as called in C++) inheritance.

#### Repeated inheritance
```
   class D repeated {
     ...
   }
   
   class B inherits D {
     ...
   }
   
   class C inherits D {
     ...
   }
   
   class A inherits B and C {
     ...
   }
```
```
   class D {
     ...
   }
   
   class B inherits repeated D {
     ...
   }
   
   class C inherits repeated D {
     ...
   }
   
   class A inherits B and C {
     ...
   }
```
#### Shared inheritance
```
   class D shared {
     ...
   }
   
   class B inherits D {
     ...
   }
   
   class C inherits D {
     ...
   }
   
   class A inherits B and C {
     ...
   }
```
```
   class D {
     ...
   }
   
   class B inherits shared D {
     ...
   }
   
   class C inherits shared D {
     ...
   }
   
   class A inherits B and C {
     ...
   }
```

#### Repeated inheritance declared in parent class
Repeated inheritance is the default an does not need to be explicitly declared.
```
   class D {
     ...
   }
   
   class B inherits D {
     ...
   }
   
   class C inherits D {
     ...
   }
   
   class A inherits repeated B, C {
     ...
   }
```
#### Shared inheritance declared in parent class

This is the same mechanism as in C++ and included for compatibility with C++ declaration and semantics.
```
   class D {
     ...
   }
   
   class B inherits D {
     ...
   }
   
   class C inherits D {
     ...
   }
   
   class A inherits shared B, C {
     ...
   }
```
### virtual inheritance

Virtual inheritance allows a nested class to be overriden in inheriting classes
```
   class C {
       virtual class V {
           ...
       }
       ...
       var v : V
       ...
   }
```
here class D inherits from class C and extends the virtual class C::V with D's V :-
```
   class D : C {
       extend virtual class V {
           ....
       }
   }
```
here class E inherits from class C and overrides the virtual class C::V with E's V :-
```
   class E : C {
       override virtual class V {
           ....
       }
   }
```
here class F::V will be flagged as an error :-
```
   class F : C {
       virtual class V {
           ....
       }
   }
   
```

## subjects under inheritance

### class

### signature

### interface

### enumeration

### record

### variant

### datatype

### module

### package

# Syntax

*ClassDeclaration* = **class** *ClassName* [ (**shared** | **repeated**)
[**only**] ] *ClassInheritance*  *MixinClause*  *ImplementsClause*  *ClassBody*

*ClassInheritance* = [ *ExtendsClause* ] [ *InheritsClause* ]

*ExtendsClause* = **extends** ( *ClassName* | *Type* )

*InheritsClause* = (**inherits** | **:**) [ **flatten** ] [ *ClassName* [ **shared** | **repeated** ]  ( **,** *ClassName* [ **shared** | **repeated** ])*

*ImplementsClause* = [ **implements** *InterfaceOrSignature* ( *,* *InterfaceOrSignature*)\* ]

*InterfaceOrSignature* = *InterfaceName* | **signature** SignatureName

*MixinClause* = **mixin** *MixinName* ( **,** *MixinName* )\*

*ClassBody* = **{** ... **}**

# Semantics

todo
