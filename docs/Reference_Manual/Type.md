Type
----

## Type System
The type system is based on the type system of Sorts that Pure Type Systems use, combine with the concept of Type Lattices for each type domain.

### meets
A meet is denoted a ∧ b or a | b

Meets are equivalent to disjoint unions as used in Algebraic Data Types and are also used semantically to found both varients and binary level unions from the top view withint the language semantics.

### joins
A join is denoted as a ∨ b or a + b

joins are structural combinations and are used in some forms of inheritance and multiple inheritance, where order semantics are not used.

### any, top, undefined, and bottom
```
  type any = top
  type undefined = bottom
```
## Type Definitions

Type definitions are opaque by default.

### Opaque Types
Structural access to data structures and member types are not allowed with opaque types.

**opaque** types hide the type they are implement using and will not allow implicit conversions to and from them, requiring coersion if this is needed.


`   opaque type A = B;`

### Transparent Types
Structural access to data structures and member types are allowed with transparent types.

**transparent** types allow implicit conversion between them and the type they are defined by.

`   transparent type A = B;`

## Generic Instatiation
`   type integerVector = vector(integer);`

## Type Anchors
### like

**like** type anchor
```
  class A {
      method m( b : like A) {
          ...
      }
  }
```
This works for references and value types.
```
  class A {
      var b : ref like A
      ...
  }
```
This obviously only works for references and pointers.
The following will cause a compile time error to prevent runtime infinite recursion on initialization.
```
  class A {
      var b : ref like A = new like A
      ...
  }
```
### Self
```
  class A {
      method m( b : Self) {
          ...
      }
  }
```
### covariance and contravariance ###

## Syntax ##
### Syntatic Sugar ###
## Semantics ##
## Pragmatics ##
Programmatic Unicode Keyboard Support for OS'es to map ctrl '<' onto '∧' and ctrl '>' onto '∨'.
