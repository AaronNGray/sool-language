ref[erence]
-----------

References are a builtin parameterized type. References are invariant.

### typed referances

'reference to T' is syntatic sugar for 'reference(T)'

`    var ri : ref integer = i`

### untyped references

Untyped references are anchored by the sources type, which maybe
dynamic.

`    ref r = x`

### const references

`    const ref cr = x`

`    const cr : const ref = x`

### by ref

By default most objects are passed around by reference by default unless
they are base types, declared as value types, or specifically passed by
value in a routines signature.

### by value
```
    class point by value {
    protected:
        var x:integer
        var y:integer
    public:
        constructor point(x:integer, y:integer) {
            self.x = x
            self.y = y
        }
    }
```

'value of t' is syntatic sugar for 'value(t:in ref T)'.

### in ref

in ref's are contravariant.

### out ref

out ref's are covariant.

Syntax
------

Semantics
---------
