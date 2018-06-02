this is really really rough...

### Object
```
 class Object : object {
 compiletime:
   name : identifier
   class : ref Class
   size = sizeof runtime
 runtime:
   class : ref Class
 }
```
**Object** knows its **Class**. **Object** inherits from object. The default **Object** has a **map**, a 'vtable', or uses a 'papaf'

### object

'object' does not know its class. It is simply a fixed sized memory area
indexed by a map.
```
 type object(env size:size) {
 compiletime:
   type type = ...
   var map : map( name, type, offset)
   getter( name) : ref object
   setter( name, ref object)
 runtime:
   var data : byte[size]
 }
```
size comes either from the parents environment (outer object) or is passed as a parameter from the parents constructor.

```
 type struct(env size:size) {
 compiletime:
   var map : map( name, type, offset)
   getter( name) : ref object
   setter( name, ref object)
 runtime:
   var data : byte[size]
 }
```


### dynamic objects
```
 type dynamic object {
 runtime:
   type slot : object | ref dynamic object
   map : map( name, index)
   value[] : slot
 }
```
```
 dynamic object aDynamicObject {
   slot a : any
   ...
 }
```
### prototypical objects

Not sure this is needed with the existance of 'dynamic objects' :-
```
 prototypical object aPrototypicalObject : parentPrototype {
   ...
 }
```
The following gives access to all the methods in an object as an
associative array :-

`  var methods = self.method`

The following gives access to a specific method :-

`  self.method["aMethod"]`

`  var methodName:string = "aMethod"`

`  var aMethod:method = self[method methodName]`
