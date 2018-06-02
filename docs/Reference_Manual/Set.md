## set ##
Sets will be designed to sematically mimick mathematical sets as is far as is possible within the SOOL language framework. Pure set like syntax should then be able to be implemented at a later stage once SOOL/Tesseract has typesetting.

### operations ###

```
signature set(T:any) {
  constructor empty() : Self
  method has member (t: ref T) : boolean
  method add member (t: ref T) : boolean
  method remove member (t: ref T) : boolean
  method complement() : Self
  method union(s: set(T)) : Self
  method intersection(s: set(T)) : Self
  method difference(s: set(T)) : Self
  method symetric difference (s: set(T)) : Self
  static method complement(s: set(T)) : Self
  static method union(lhs: set(T), rhs: set(T)) : Self
  static method intersection(lhs: set(T), rhs: set(T)) : Self
  static method difference(lhs: set(T), rhs: set(T)) : Self
  static method symetric difference (lhs: set(T), rhs: set(T)) : Self
}
```

### static enumerated sets ###

`  type walls = set { north, south, east, west}`

or

`  set walls = { north, south, east, west}`

### typed sets ###
Sets of integers are an example of typed sets

`  var aSetOfIntegers : set of Integer`

### generically typed sets ###
`  set(T is enumerable)`

## Syntax ##

## Semantics ##

## Implementation ##
Sets are implemented using a fixed for static sets or extensible vector of booleans or for sparce sets a sorted vector or trie of integers mapping to elements
