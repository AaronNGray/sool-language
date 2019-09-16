## Signatures

Signatures are like traits but unlike traits they are implicit, non atomic, and non manifest.

```
 signature aSig {
   function aFunction( i:int):void;
   function anotherFunction():int;
 };
```

Signatures allow generic and templated objects to be type checked, before instantiation.

```
 signature Comparable(T) {
   operator > (lhs:T, rhs:T):bool
 };
```
```
 generic (T: Comparable)
 function max(a:T, b:T):T {
   return a > b ? a : b
 }
```

### ... is ...

```
 function max(T is Comparable)(a:T, b:T):T {
   return a > b ? a : b
 }
```

###

```
 signature Sortable(T(E is Comparable) is OrderedCollection)

 signature Sequence is OrderedCollection
```
### ... of ...
```
 signature Sortable(T is OrderedCollection of Comparable)
```

## has and optional keywords
```
 signature aSignature {
   optional function anOptionalFunction() { ... }
   ...
 }
```
static usage
```
   ...
   static if S has function anOptionalFunction { ... }
   ...
```

dynamic usage
```
   ...
   if S has function anOptionalFunction { ... }
   ...
```
where S is a module or a namespace or trait or signature.

### Inheritance

Signatures maybe "instantiated" as traits. This is done by the trait inheriting the signature or signatures.

## Implementation

**optional** and **has** keywords can be implemented easily staticly. The dynamic **if** case has much reduced overhead in implementing classes compared to full reflective meta class information. Implementation of **has** is reduced to a referencing a **boolean** in the class object heirachy in the dynamic case and normalizes out as a constant in the static case.

## Influences

Adding the **optional** keyword to signatures and **has** keyword to conditionals was influenced by The D Language.

## History
As far as I know signatures were orignated by Robin Milner in Standard ML (Meta Language).

## Syntax


## Semantics

