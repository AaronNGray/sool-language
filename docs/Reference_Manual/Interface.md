##Interfaces

Declaring an interface :-
```
 interface anInterface {
   method aMethod(i:int):void
   method anotherMethod():int
 }
```
Using an interface, the following are all equivalent :-
```
 class aClass : anInterface {
   ...
 }
```
```
 class aClass implements anInterface {
   ...
 }
```
```
 class aClass {
   implements anInterface
   ...
 }
```
Declaring interfaces within a class
```
 class aClass {
   interface an interface {
     ...
   }
 }
```
### Facade ###
Declaring two facades within a class
```
 class aClass {
   facade aFacade {
     method aMethod():void
   }
   facade anotherFacade {
     method aMethod():void
   }
   ...
 }
```

Todo facade access and explanation.

These two methods are independant and are in there own sub scope.

###inheritance
```
 interface anotherInterface : anInterface {
   method yetAnotherMethod():void
 }
```
or
```
 interface anotherInterface {
   inherit anInterface
   method yetAnotherMethod():void
 }
```

##Syntax

##Semantics
