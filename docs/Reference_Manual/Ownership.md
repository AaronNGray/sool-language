## Ownership
Ownership, lifetime, and burrowing semantics for SOOL.

### Class Member Ownership
Here classs A owns b of class B
```
 class A {
    owner b:B
    ....
 }
```
### Class Instance Ownership
Here class A owns all its members.
```
 class A owner {
     var b:B
     var c:C
 }
```

**not** **owner** may be used for exceptions under normal full class member ownership.

### Semantics

#### Move Semantics
Move semantics can be acertained by usage.
#### Copy Semantics
Copy semantics needs to be looked at.
#### Lifetime analysis
Lifetimes can be established by usage and the traditional compiler technique of dataflow analysis.

### Lifetimes
Lifetimes will generally be established by scope.
```
 function f() {
     let v = vector ([1, 2, 3])
     ...
     // do something with v
     ...
 }
```
Here v is automatically deallocated from the stack and heap storage freed since there are no outgoing dataflow transitions when analysed by dataflow semantics.
```
 function g() {
     let v = new vector ([1, 2, 3])
     ...
     // do something with v
     ...
     delete v
 }
```
```
 function h() {
    let v = new vector ([1, 2, 3]) 
    ...
    // do something with v
    ...
 }
```
Here since v's ownership is not passed out of the function it can be established at compile time that there is a memory leak.

Use after free can also be established by dataflow analysis on references.

## Syntax

## Semantics

## Notes
Rust's capture of passed variables seems a little dictotorial and overzelous at the least. Converting or using existing code and algorithms in Rust could be difficult as a result.

One of the main aims of SOOL is to allow both transcription of existing code and algorithms from existing sources and semantic subsumption of existing code.

Normal proceedural burrowing maybe established by pass by reference and syncronous call semantics.

Rust's case maybe provided by using the owner keyword attribute on the function signature to transfer ownership.

I am still deliberation over using own, owns, and owner keywords.
