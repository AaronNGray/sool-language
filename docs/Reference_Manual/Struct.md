##struct

**struct**s are POD's or **P**lain **O**ld **D**atatypes. They only
contain non types data and are part of the System Platform(s) dependant
subsystem.

They maybe endian, i.e. **bigendian** or **littleendian**.
```
 struct S bigendian align(byte) {
   var i : int(8)
   var l : int(32)
 }
```

##Struct

**Struct**s are POD's but with the extension of non virtual methods.
