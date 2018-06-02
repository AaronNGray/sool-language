## Arrays

Arrays are parameterized types with syntatic sugar.

### unbound arrays

` array of T`

### bound arrays

` a: array[1..10] of integer`

is syntatic sugar for

` a: array(1..10, integer)`

1 based array

` array[1..N] of T`

0 based array

` array[0..N] of T`

### extensible arrays

0 based extensible array

` array [0..] of T`

1 based extensible array

` array [1..] of T`

### bidirectional arrays

` array [..0..] of T`

` array [..] of T`

### multi-dimentional arrays

` a: array[1..10, 0..20] of integer`

is syntatic sugar for

` a: array((1..10, 0..20), integer)`

multi-dimentional extensible arrays

` array [0..,1..] of int`

*multi-dimentional extensible arrays may use Cantors diagonalization mapping, but thats a library implemetation decision.*

### bit arrays
```
 union {
   byte
   bit: array [0..7] of bit
   boolean: array [0..7] of boolean
 }
```
### initializers

` var ai: array of integer = { 1, 2, 3, 4, 5, 6, 7, 8, 9}`

` var as = new string[] { "Small", "Medium", "Large" }`

## Implementation

## Syntax


## Semantics
