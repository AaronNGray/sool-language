## C++ Compatibility Extensions

### Introduction
It is intended as an extension to SOOL to allow C++ code to be both translated and C++ modules to be imported. This requires dealing with the sematicns and pragmatics of the C++ Language. Requiring for post translated code either to allow koenig lookup to be specified by keyword for the SOOL code or to convert and "markup" parameter types. This will allow both the calling of C++ code using koenig lookup and SOOL code that has been specified as using koenig lookup.

### Koenig lookup
```
 import C++.koenig
```

#### Modules
```
 module X koenig {
   ...
 }
```

#### Class
```
 class Y koenig {
   ...
 }
```
#### Method
```
 method aMethod (...):void koenig {
   ...
 }
```

#### Operator
```
 operator "=" (...):T koenig {
   ...
 }
```

## Implementation
Once SOOL is bootstrapped in itself and is able to use pattern matching on its program AST then koenig lookup semantics should be relatively easy enough to implement in theory.

