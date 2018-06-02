### List constructor

`   datatype list(T) = null | cons(T, list(T))`

`   list of T`

### List operations

```
 e = head(l)
 e = l.head()

 l2 = tail(l)
 l2 = l.tail()

 l2 = front(l)
 l2 = l.front()

 e = back(l)
 e = l.back()

 append(l, e)
 l.append(e)

 concat(l1,l2)
 l.concat(l2)

 l2 = map(l, f)
 l2 = l.map(f)

 l2 = foldl(l,f,s)
 l2 = foldr(l,f,s)
```
