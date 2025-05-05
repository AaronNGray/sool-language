# Range

An integer range is defined

```
i : integer 1..10
```

A range :-

```
type r = range 1..10
```

```
type range(T) {
  constructor syntax lower ".." upper instantiate {
    lower : T
    upper : T
  }
}
```
A extended definition of range is defined as :-

```
type range(scalar T) = {
  lower:T
  upper:T
}
type range(T is scalar) = {
  lower:T
  upper:T
}
type range(T:character) = {
  lower:T
  upper:T
}

refine type range(any) {
  begin alias lower
  end alias upper
}
```

```
v "is" t = is(t:Type)(v:T):boolean = typeof v == t
```
```
type scalar = subtype of Scalar
```


```
type range(pointer to T) = {
  begin: pointer to T
  end: pointer to T
}
type range(reference to T) = {
  begin: reference to T
  end: reference to T
}
```
