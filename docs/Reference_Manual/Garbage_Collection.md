## Garbage Collection

`  import gc( implementation : enum {implicit,explicit} = explicit)`

### usage on classes
If you specifically want gc on a class then specify **gc**
```
 import gc
 
 class aClass gc {
   ...
}
```
or
```
 import gc(implicit)
 
 class aClass {
   ...
 }
 
 class anotherClass nogc {
   ...
 }
```

### usage of constructors

usage of gc with named constructors

```
 import gc
 
 class aClass {
   constructor () {...}
   constructor gc gc (){...}
   destructor gc gc (){...}
   ...
 }
 
 var aGarbageCollectedObject:aClass.gc
```
