Platform
--------

Platform types are ...

### bit

bit and bit arrays are allowed :-

`   aBit:bit`

`   type crumb = bit[2]`

`   type nibble = bit[4]`

### byte

### word(16,18,32,36,64)

### int(32,64,128,256)

### float(32,40,48,64,80,128)

System
------

The System types are naturally system dependant, and are not defined
here.

Base
----

Base types are common to all implementations.

### bool[ean]

### natural

### integer

### real

### fraction

### char[acter]

`   aChar : char(8);`

`   aUnicodeChar : char(unicode,32);`

`   type char[acter]([unicode], bits:integer)`

### string

`   aUTF8String : string(unicode,8)`

Modifiers
---------

### const[ant]

Constant types generally do not allow 'address of' operation, unless
they are platform types, thus do not need to be manifest in the program
image, unlike C, C++.

### volatile

Only platform and system types allow the volatile modifier.

### register

Only availiable with platform module. If the variable name is the same
as a register then it will use that register if possible. If the
variable name is a register and is a parameter to a function then again
it will be assigned to that register.
