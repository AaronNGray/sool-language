## Iterator ##

### Illustrative Example ###

The following is mearly to paint a picture of what is possible in SOOL. Parenthesis for parametres maybe missed out if there are no parameters.

```
  signature Iterator(T:any) {
    method deref : ref T
    operator pre ++ () : Self
    operator post ++ () : Self
    operator pre -- () : Self
    operator post -- () : Self
  }
```
```
  signature ClassWithIterator(T:any) {
    ...
    method begin() : signature Iterator(T)
    method last() : signature Iterator(T)
    method end() : signature Iterator(T)
    ...
  }
```
```
  class aClassWithIterator : signature ClassWithIterator(integer) {
    ...
    var t : array of integer
    ...
    class iterator : signature Iterator(integer) {
      method deref : ref integer = t[index]
      operator pre ++ () : Self {
        ++index
        return self
      }
      operator post ++ () : Self {
        var old = self
        ++index
        return old
      }
      operator pre -- () : Self {
        --index
        return self
      }
      operator post -- () : Self {
        var old = self
        --index
        return old
      }
      var index : integer
    }
    ...
    method begin : iterator = t.begin
    method last : iterator = t.last
    method end : iterator = t.end
    ...
  }
```
