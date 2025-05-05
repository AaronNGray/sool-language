# struct
```
type struct {
compiletime:
    var size : size
    var indexMap : map( name, index)
    var typeMap : map( name, type)
    var offsetMap : map( name, offset)
    getter( name) : type
    getter( name) : offset
    setter( name, (type, offset))
    setter( name, type)
    setter( name, offset)
    
    getter( name) : compiletime typed ref
    getter( name) : runtime typed ref
    
runtime:
    var data : byte[size]
}

type value object (T subtype of object) {
compiletime:
    constructor (value : T) instatiate
    constructor (ref : ref T) { value = ref }
    getter() : Object
    getter() : value T
    getter() : type
    setter( Object) throws InvalidType
    setter( object)
runtime:
    value : T
}

type ref object (T subtype of object) {
completime:
    constructor (ref : ref T) instantiate
    constructor (value : T) { ref = ref value }
    getter() : ref T
    getter() : type
    setter( Object) throws InvalidType
    setter( object)
runtime:
    ref : ref T
}

type ref (T subtype of any) {
    ....
}

type Ref (T subtype of Any) {
    ....
}

type any = top object
type Any = top Object
```
