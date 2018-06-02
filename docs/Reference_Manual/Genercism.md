## Generacism ##
Generacism allow compile time obejects to be parameterized. SOOL's parameterization will be much more complete than C++'s or Java's. Consistency between builtin base types and classes will allow seemless usage of generacism. Specialization of generic classes and generic methods and operators as well as overloading of generic parameters should lead to a much more complete parameterization space.

### Generic Objects ###
The range of compile time objects that can be used under generacism is completely satified.

#### Classes
```
generic (T:T) class aClass {
  ... T ...
}
```
##### Specialization
```
generic (T:any) class vector (pointer to T) {
  ... T ...
}
```
#### Methods
```
generic (T) 
function append(a:List(T), b:List(T)):List(T) {
  match (a) {
    case nil:
      return b;
    case cons(hd, tl):
      return cons(hd, append(tl,b));
  }
}
```
##### Specialization

#### Operators
```
generic (T) 
operator :: | function cons (lhs:List(T), rhs:List(T)):list(T) {
  match (lhs) {
    case nil:
      return rhs;
    case hd :: tl:
      return hd :: (tl :: rhs);
  }
}
```
#### Types

#### Arrays

#### Records

#### Variants

#### Interfaces

#### Signatures

#### Functions

#### Objects

#### Templates

Generic Templates allow generic parameterization as well as template parameterization. As said generic parameters are part of the objects identity or signature, where as template parameters are not, they only exist within the templates body.

### Generic Parameters ###

Generic Parameters are generally restricted and probably will be for all initial implementations. The use of the **any** type "restriction" opens parameterization up to the same level as C++'s template parameterization model. This is almost like a dynamic languages approach to object dispatch but at compile time in a static language.

Restricted genericity allows proper parsing of generic object declarations just post parse time for semantic analysis, rather than delaying semantic analysis to instantiation time which is the problem with C++'s templates and the **any** parameter model. 

Generic parameters maybe instantiated with types and be restricted with signatures, interfaces or domains. They may also have default values.

Multiple generic specifications maybe specified and even overlap in type domain with the last being the implementation chosen as the most specialized.

#### Types

#### Interfaces

#### Domains

#### Generics
Generic generic parameters
```
  generic(T:any, C:generic(T) class = vector)
  class Stack {
    var elements : C(T)
    method push(value : ref const T):void
    method pop():ref const T
    method top():ref const T
  }
```
Note **any** can be used here in this context with no parsing overheads as there are no direct applications to its object and is thus typesafe.

#### Templates

Generic template parameters.

#### auto / any

This is to support C++ like template parameters. It is not sure whether this will be implemented as the parsing costs are great.

#### varadic parameters

```
class A(...) {
    method test(...:...) {
        foreach(a in ...) {
            print a.tostring() + "\n"
        }
    }
}
```

notice how the genericism turns into polymorphism in the foreach statement.

#### Default Generic Parameters

Default types maybe used as default parameters, these maybe constants or be provided by a higher scope type variable.

### Generic Arguments ###

#### Types

##### Base Types

##### Classes

##### Abstract Data Types

#### Signatures

Although signatures may not be instantiated directly they maybe used for further specification of restrictions of contained generic objects.

#### Interfaces

Again like signatures that may not be instantiated directly interfaces maybe used for further specification of contained generic objects.

#### Domains

#### Generics

#### Templates

Generic template arguments.

#### auto / any

#### varadic arguments

A number of arguments maybe specified of a type to satisfy the variadic generic parameter type.

#### Default template arguments

##### No arguments

If no arguments are necessary and all arguments values are default generic parameter values then no parenthesis are required. And the generic type appears as an unparenthesised type like any normal type specifier.

### Overloading ###
Since they are bounded on another level by signatures and other kinds generic declarations maybe overload.

### Compound declarations ###

Braces may be used to allow multiple generic objects to be declared within the same parameter space.
```
generic (T:T) {
  class A {
    ...
  }
  class B {
    ...
  }
}
```
## Syntax ##

## Semantics ##
generacism is a **kind**.

### Implementation Semantics

Generics may be implemented in a number of ways either guided be the programmer in the modules implementation file, or by the implementation. Generics maybe implemented using either polymorphism or with multiple instantiations by lowering to templating.
