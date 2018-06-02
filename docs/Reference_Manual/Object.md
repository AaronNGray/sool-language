Objects
-------

### Anonymous objects

`  var o : Object = new { Amount = 108, Message = "Hello" }`

### Augmented objects
```
 var count : Integer {
   method clear() { self = 0 }
   method incerment() { ++self }
 }
```
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
**Object** knows its **Class**. **Object** inherits from **object**. The default **Object** has a 'map, a 'vtable', or uses a 'papaf'

### object

**object** does not know its **class**. It is simply a fixed sized memory area indexed by a compile time **map**.
```
 type object(env size size) {
 compiletime:
   var map : map( name, type, offset)
   getter( name) : ref object
   setter( name, ref object)
 runtime:
   var data : byte[size]
 }
```
size comes either from the parents environment (outer object) or is passed as a parameter from the parents constructor.
