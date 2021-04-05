## Macros

macros allow parameterized code snippets to be generated. Templates cannot really be used for this as they are integral semantic units. macros on the other hand are syntatic and syntatically complete, and thus still hygenic.
```
 macro foreach(c:C is collection)
 specialization (c:dictionary) {
   ...
 }
 specialization (c:list) {
   ...
 }
```
