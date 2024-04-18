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
```
 datatype d inherits a = D {
   ...
 }
```
Datatype *d* inherits *a* and adds sub type *D*.
## Generalized Algebraic Data Types (GADT's)

GADT's will not be implemented in the first implementations due to their complexity.
