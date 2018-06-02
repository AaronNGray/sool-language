Tuples
------

Tuples are first class citizens

```
 tuple t = (a:A, b:B, c:C)
```

### Semantics

#### Static

<tex>

\\inference{

`   \Gamma \vdash x_0 : T_0 \thinspace`
`   ... \thinspace`
`   \Gamma \vdash x_n : T_n`

}{

`   \Gamma \vdash ( x_0, x_1, ..., x_{n-1}, x_n ) : T_0 \times T_1 \times ... \times T_{n-1} \times T_n`

}[TupleConstructor]

</tex>

Deconstruct a tuple into a record :-

<tex>

\\inference{

`   \Gamma \vdash x_0 : T_0 \thinspace`
`   ... \thinspace`
`   \Gamma \vdash x_n : T_n \\`
`   \Gamma \vdash ( x_0, ..., x_n ) : T_0 \times ... \times T_n \\`
`   \Delta \vdash l_0 : Lable \thinspace`
`   ... \enspace`
`   l_m : Lable \\`
`   l_h \mapsto x_i`

}{

`   \Gamma ; \Delta \vdash \{ l_0 : T_j = x_j, ... , l_m : T_k = x_k\}`

}[TupleDeconstructor]

</tex>

#### Dynamic
