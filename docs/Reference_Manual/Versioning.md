## Versioning ##
SOOL allow versioning of all major elements from packages, and modules down to structs and unions.

```
version 1.0.0 struct aStruct {
    ...
}
```
```
version 1.0.0-1.9.0 struct aStruct {
    ...
}
```
```
version 1.0-10.0 struct aStruct {
    ...
}
```
Compound
```
struct aStruct {
    version 1.0.0 {
        ...
    }
    version 2.0.0 {
        ...
    }
}
```
Partial
```
struct aStruct : anotherStruct {
    ...
    var a:int
    ...
    version 1.0.0 {
        delete b
        rename c as d
        remap e as int
    }
    ...
}
```
or remapping of individual members
```
struct aStruct {
    ...
    version 1.0.0 delete a
    ...
    version 1.0.0 rename b as c
    ...
    version 1.0.0 remap d as int
    ...
}
```
