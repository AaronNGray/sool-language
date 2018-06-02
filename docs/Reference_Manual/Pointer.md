Pointers
--------

Pointers are not normally availiable in the base prelude and language. You need to import the system.platform module or the pointer module.

` var i : integer`

` var pi : pointer(integer) = addressof(i)`

**ptr** is short hand for **pointer**

` var s : string`

` var ps : ptr to string = address of s`

### pointer to

**ptr to A** is syntatic sugar for **pointer(A)**

` syntax TypeExpression := ("pointer" | "ptr") ["to"] e:TypeExpression -> pointer(e)`

### address of

` This : pointer to Self`

` this = address of self`

### pointer arithmatic

### sizeof()

### nullptr

### nullable

Pointers are not allowed to be null by default **nullable** gets over this "problem".

` var pi : nullable ptr to integer = nullptr`

nullable pointers do not necessarily need initializing, although this is bad practice. All no nullable pointers need initializing on declaration.
 
### Exceptions

#### NullPtrAssigment

##Syntax


##Semantics
