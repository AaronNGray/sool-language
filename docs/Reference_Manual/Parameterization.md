# Parameterization

## Value Parameterization

## Type Parameterization
### explicit parameterization
#### generic function
The following are all equivalent
```
  generic (type T)
  function f(t:T):T {
    ...
  }
```
```
  generic (T:type)
  function f(t:T):T {
    ...
  }
```
```
  generic (T:any)
  function f(t:T):T {
    ...
  }
```

#### generic class
```
generic (type T)
class C {
  method m(t:T):T {
    ...
  }
}
```
#### generic concept
```
generic (type T)
concept C {
  method m(t:T):T {
    ...
  }
}
```

### implicit parameterization

### generic function
In implicit generic parameterization the compiler deduces the type by type inference and it does not have to be declared explicitly.
```
  generic {type T}
  function f(t:T):T {
    ...
  }
```
This is simular to C++ function templates.

#### generic class
```
generic 
class C {
  type T;
  method m(t:T):T {
    ...
  }
}
```
```
generic {type T}
class C {
  method m(t:T):T {
    ...
  }
}
```
#### generic concept
Internally declared generic type
```
generic 
concept C {
  type T;
  method m(t:T):T {
    ...
  }
}
```
Externally declared implicit generic type
```
generic {type T}
concept C {
  method m(t:T):T {
    ...
  }
}
```
