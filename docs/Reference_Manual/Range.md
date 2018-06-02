An integer range is defined

`   integer 1..10`

A range is defined as :-
```
    type range(scalar T) = {
        constructor syntax T lower ".." upper instantiate
        lower:T
        upper:T
    }
    type range(character T) = {
        constructor syntax T lower ".." upper instantiate
        lower:T
        upper:T
    }
    type range(pointer to T) = {
        begin: pointer to T
        end: pointer to T
    }
    type range(reference to T) = {
        begin: reference to T
        end: reference to T
    }
```
