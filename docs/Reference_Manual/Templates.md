Templates
---------

Templates are hygienic semantic macros. They allow very powerful code generating code to be constructed.

### Templated Objects

##### Variables and Expressions

The value of an expression or variable maybe inserted into a template by escaping it by a double parenthesised expression.

#### Classes
```
 template TemplatedClass(className:string, parent:class) {
   class ((className + "Class")) : ((parent)) {
     ...
   }
 }
```
#### Methods

#### Types

#### Arrays

#### Records

#### Structs

#### Unions

#### Interfaces

#### Signatures

#### Functions

#### Blocks

The syntax clashes with the compound declaration, and a compound
statement. Might use either a 'block' keyword or use 'macro' instead

#### Objects

#### Compound
```
 template TemplateT(T:class) {
   class A : ((T)) {
     ....
   }
   class B {
     ... ((T)) ...
   }
 }
```
#### Generics

Templated Generacism allows templated generic forms to be created.

#### Templates
```
 template T(t:type) {
   template S(a:t) {
     ....((t))..((a))....
   }
   template U(b:t) {
     ....((t))..((b))....
   }
 }
```
```
 T(integer)
 S(1)
 U(2)
```
#### multiple variadic parameters
```
 template T(A ...)
   template S(B ...) {
     .... ((A ...)) .... ((B ...)) ....
   }
```
### Template Parameters

Templates maybe overloaded and have default parameters, where they do
not conflict.

#### Types

#### Signatures

```
 template T(signature s:S) {
   ....((s))....
 }
```
#### Interfaces

#### Domains

### Templates

Template template parameters.

### Generics

Template generic parameters.

#### Constants

#### References

### Compound declarations

Parentheses may be used to allow multiple layer templated objects to be
declared. This is a bit like Currying.

```
 template A(T:T)(S:S)
   ...
```
Instantiation

`   ATemplate = A(t)`

or

`   template ATemplate = A(t)`

Usage

`   ATemplate(s)`

### Template Specialization
```
 template(T:basetype) [
   aTemplate(i:integer) {
     ....
   }
   aTemplate(r:real) {
     ....
   }
 ]
```
or
```
 template aTemplate(T:basetype) [
   (i:integer) {
     ....
   }
   (r:real) {
     ....
   }
 ]
```
#### Template Partial Specialization ####

### Template Overloading ###

### Template varargs ###

##Examples
```
 template TemplatedClass(className:string, parent:class) {
   class ((className + "Class")) : ((parent)) {
     ...
   }
 }
```
basically parenthesis denote an expression. An old technique of mine called micro syntax will allow this to be implemented cleanly and "easily" in the parser.

They can either be generated and evaluated inline :-

`   TemplatedClass("Test", base)`

or be assigned to a variable :-

`   var aTestTemplatedClass:class = TemplatedClass("Test", base)`

And then be assigned to a string and outputted even.

`   var test:string = aTestTemplatedClass`

this assigning to a string goes for any language construct.

The value of an expression or variable maybe inserted into open context module code by escaping it as an paraenthesised expression, hence having it evaluated as an expression rather than as a literal.

`   import (test)`

It evaluated as an expression at compile time in static code and either at compile time or runtime in dynamic code depending on wether it evaluates to a constant or not. This is the same as The D Language's **mixin()** statement.

This is the beauty of a meta programming language !

## References

[D Language Mixin Statement](http://dlang.org/mixin.html)

##Syntax


##Semantics
Templates are kinds with added dependant types connotations. 

