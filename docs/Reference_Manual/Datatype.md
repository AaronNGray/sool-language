# Data Types
## Algebraic Data Types (ADT's)
### Introduction
Algebraic Data Types allow the representation of data as a set of alternative structual forms. They may be pimariliy be used to represent Abstract Syntax Trees for the representation of programs. For example Statements and Expressions. They may utilize recursion and mutual recustion between multiple Algebraic Data Types.

### Constructors
```
datatype boolean = true | false
```
```
datatype T =
  A(a:A)
  | B(a:A, b:B)
  | C(a:A, c:C)
```
### Pattern Matching
[match ... case ... default](match)

#### Anonymous or unnamed datatype members
Anonymous or unnamed datatype members are a normalization or unification of the space of datatypes with tuple space as used in pattern matching. 
```
datatype T =
  (a:A)
  | (a:A, b:B)
  | (a:A, c:C)
```
These fit in with both the pattern matching implementation and the implementation of MetaMorphosis with the unnamed parser generation grammar rules and their matching.

## Parameterized Algebraic Data Types (PADT's)
Parameterized Algebraic Data Types are syntatic sugar for generic parameterization.
```
datatype list(T) = nil | cons(T, list(T))
```
Parameterized Algebraic Data Types are simply generic types.
```
generic (T) datatype list = nil | cons(T, list(T))
```

## Augmented datatypes
Augmented data types allow decorating both the datatype and its disjoint type members with methods.
```
 datatype a {
   virtual x() { ... }
   virtual y() { ... }
 } =
  A {
   x() { ... }
   y() { ... }
   ...
 }
 | B {
   x() { ... }
   ...
 }
 | C {
   ...
 }
```

## Inheriting datatypes
Here datatype *d* inherits *a* and adds sub type *D*.
```
datatype d inherits a = D {
  ...
}
```
Datatype multiple inheritance allows composition of a number of datatypes.
```
datatype d inherits a, b, c
```

This can also be augmented by a functional interface.
```
datatype d inherits a, b, c {
  transform(...) { ... }
  lower<T>():T { ... }
}
```

## Generalized Algebraic Data Types (GADT's)

GADT's will not be implemented in the first implementations due to their complexity, and inability to normalize their model properly using initial algebras.

## Implementation
This shows the implementation of ADT's by lower onto [virtual classes](Class.md#virtual-classes).
```
datatype T =
  A(a:A)
  | B(a:A, b:B)
  | C(a:A, c:C)
```
**datatype**s may have implicit semantic tagging behaviour
```
type d inherits Type(T).Index =
  A : index(0), (a:A)
  | B : index(1), (a:A, b:B)
  | C : index(2), (a:A, c:C)
```
maps to a virtual class implementation
```
class T {
  virtual class A {
    a:A;
  }
  virtual class B {
    a:A;
    b:B;
  }
  virtual class C {
    a:A;
    c:C;
  }
}
```
implicit tagging implementation
```
class T inherits Type(T).Index {
  virtual class A : index(0) {
    a:A;
  }
  virtual class B : index(1) {
    a:A;
    b:B;
  }
  virtual class C : index(2) {
    a:A;
    c:C;
  }
}
```
### Anonymous or unnamed datatype members
Anonymous or unnamed datatype members. 
```
datatype T =
  (a:A)
  | (a:A, b:B)
  | (a:A, c:C)
```
implementation
```
class T inherits Type(T).Index {
  virtual class _ : index(0) {
    a:A;
  }
  virtual class _ : index(1) {
    a:A;
    b:B;
  }
  virtual class _ : index(2) {
    a:A;
    c:C;
  }
}
```
## Syntax

## Semantics
