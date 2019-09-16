## Signatures

Signatures are like interfaces but unlike interfaces they are implicit, non atomic, and non manifest.

```
 signature aSig {
   method aMethod( i:int):void;
   method anotherMethod():int;
 };
```

Signatures allow generic and templated objects to be type checked, before instantiation.

Signatures maybe "instantiated" as interfaces. This is done by the interface inheriting the signature or signatures.

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
   optional method anOptionalMethod() { ... }
   ...
 }
```
static usage
```
   ...
   static if C has method anOptionalMethod { ... }
   ...
```

dynamic usage
```
   ...
   if C has method anOptionalMethod { ... }
   ...
```
## Implementation

**optional** and **has** keywords can be implemented easily staticly. The dynamic **if** case has much reduced overhead in implementing classes compared to full reflective meta class information. Implementation of **has** is reduced to a referencing a **boolean** in the class object heirachy in the dynamic case and normalizes out as a constant in the static case.

## Influences

Adding the **optional** keyword to signatures and **has** keyword to conditionals was influenced by The D Language.

## History
As far as I know signatures come from Robin Milner's Standard ML (Meta Language).
*They should have been in C++ as soon as its warped generacism stroke templating was introduced.*

## Syntax


## Semantics

