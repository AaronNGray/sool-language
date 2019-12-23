## Methods

### overloading
```
 class A {
   method test(a:A):int { ... }
   method test(b:B):int { ... }
 }
```
### virtual methods
```
 class A {
   virtual method test(a:A):int { ... }
 }
```

### abstract methods

Abstract methods have no implementation and thus are used in abstract classes. And are implemented in subclasses by virtual methods.
```
 abstract class A {
   abstract method test(a:A):void
 }
```
### multiple dispatch
```
 class A {
   virtual method test(virtual b:B):int { ... }
   virtual method test(virtual c:C):int { ... }
 }
```

### static methods
```
 class A {
   static method aStaticMethod():void { ... }
   ...
 }
```
### nested functions
```
 class A {
   method test(i:int):int {
     return test2(i)
     
     function test2(i:int) {
       return i + 1
     }
   }
 }
```
### varadic parameters
```
 class A {
   method test(...) {
     foreach(a in ...) {
       print a.tostring() + "\n"
     }
   }
 }
```

### getters and setters
#### get()
#### set()
#### default
default value
#### isset()
**isset** is false if the value is the default value for its type.
#### unset()

```
 class X {
   var i : int {
     method set(i : int) {
       if (i < 10)
         ii = i
       else
         ii = 10
     }
     method get() : int {
       return ii
     }
     method isset() : boolean
   }
 private:
   var ii : int = 0
 }
```
### validators
```
 class X {
   var evenValueOnly : int {
     method validate(i : int) : boolean {
       return i % 2 == 0
     }
   }
   var i : = 0
 }
```
*need usage patterns*
### update method and event
```
 class X {
   var watchedVariable : int {
     method update( i : int) {
       listener.update( class X, var watchedVariable, i)
     }
   }
   
   var listener : listener
 }
```
*need a standard default definition of listener*
### self

explicit declaration of **self**
```
 class B {
   var x:int
   method test(self:Self, i:int) { self.x = i }
 }
```
### this

explicit declaration of **this**
```
 import system.platform.(pointers, this)
 
 class C {
   var x:int
   method test(this:This, i:int) { this->x = i }
 }
```

## Syntax


## Semantics
