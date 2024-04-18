## Algebraic Data Types (ADT's)

`  datatype boolean = true | false`

## Parameterized Algebraic Data Types (PADT's)

`  datatype list(T) = nil | cons(T, List(T))`

## Augmented datatypes
```
 datatype a = A {
   x() { ... }
   y() { ... }
   ...
 }
 | B {
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

GADT's will not be implemented in the first implementations due to their complexity, and inability to normalize their model properly.
