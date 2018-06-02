Closures
--------

### anonymous functions or lambdas

Anonynous functions have access to the enclosing scopes variables, parameters, or enclosing objects instance, the objects class variables, and module objects and classes; and module meta data.

static
```
  g(function():string { return "test" } )

  function g(f:function():string):string {
    return f()
  }
```
dynamic
```
  g(function() { return "test" } )

  function g(f) {
    return f()
  }
```
### anonymous methods

Anonynous methods are like anonymous functions but have access to the evaluating objects members. This maybe possible in limited closed modules as well as in dynamically evaluated code.

```
  g(method (signature aSignature)::aMethod(...):string { ... } )

  function g((signature aSignature)::f(...):string):string {
    return f(...)
  }
  function g((subclass of aClass)::f(...):string):string {
    return f(...)
  }
```
### nested functions

Nested functions or methods have access to the enclosing scopes variables, parameters, or enclosing objects instance and class variables, and module objects and classes; and module meta data.

### nested classes

Unlike C++ nested class instances have access to the parent classes public instance members.

When such a closure reference exists AND the nested class is instantiated from within an object instance of the enclosing class the constructor passes a hidden reference to the enclosing classes object.

### nested classes in functions

Nested classes within functions and methods have access to the functions local variables and parameters.

### anonymous classes

Anonymous classes have access to the enclosing function or methods variables and parameters or the enclosing objects instance variables.

## Implementation

Value based/type input only parameters may be folded into the code, when simple types. Where as more complex structures will be accessed by reference.

Reference based parameters must in most cases become references or pointers to the outer object being referenced. This object may be allocated on the stack or the heap depending on the life times of the closure reference and the object being referenced.

An object, function or method using multiple closure references a closure context object is created with all the references and possibly shortcut references to specific context members after profiling.

Using the heap and reference counting might be a simple and safe catch all for short term implemetations. Otherwise proper lifetime analysis in necessary.

## Syntax


## Semantics

