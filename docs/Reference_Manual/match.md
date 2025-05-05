## match...case...default...

**match** constructs maybe statements or expressions.

### match statements
```
match a {
    case a:A {
        ...
    }
    case b:B {
        ...
    }
    case c:C {
        ...
    }
    default d {
        ...
    }
}
```
### match expressions
```
a' = match b {
    case a:A ( ... a ... )
b    case b:B ( ... b ... )
    case c:C ( ... c ... )
    default d ( ... d ... )
}
```

### syntax

#### statement

Statement ::= **match** Expression **{** { **case** PatternOfNamedVariables Statement }* [ **default** Statement ] **}** 

Statement ::= **match** TypeExpression **{** { **case** Pattern Statement }* [ **default** Statement ] **}** 

Statement ::= **match** Expression ":" TypeExpression **{** { **case** Pattern Statement }* [ **default** Statement ] **}** 

#### expression

Expression ::= **match** Expression **(** { **case** PatternOfNamedVariables **(** Expression **)** }* [ **default** **(** Expression **)** ] **}** 

Expression ::= **match** TypeExpression **(** { **case** Pattern **(** Expression **)** }* [ **default** **(** Expression **)** ] **}** 

Expression ::= **match** Expression ":" TypeExpression **(** { **case** Pattern **(** Expression **)** }* [ **default** **(** Expression **)** ] **}** 

### semantics

Needs further work on tuples, etc, to express them in case statements.

#### static

##### statement

<tex>

\\inference{

`   \Gamma \vdash x_0 : T_0 \enspace`
`   \Gamma \vdash x_1 : T_1 \thinspace`
`   ... \thinspace`
`   \Gamma \vdash x_n : T_n \enspace`
`   \Gamma \vdash x_n : T_{n+1} \enspace`

}{

`   \Gamma \vdash {\bf match} \enspace x_0 : T_0 \enspace `` : void`

}[MatchStatement]

</tex>

##### expression

<tex>

\\inference{

`   \Gamma \vdash x_0 : T_0 \enspace`
`   \Gamma \vdash x_1 : T_1 \thinspace`
`   ... \thinspace`
`   \Gamma \vdash x_n : T_n \enspace`
`   \Gamma \vdash x_n : T_{n+1} \enspace`

}{

`   \Gamma \vdash {\bf match} \enspace x_0 : T_0 \enspace `` : \sqcap _{1\geq n \geq x+1} T_n`

}[MatchExpression]

</tex>

#### dynamic

##### statement

##### expression

### Implementation
Implementation of matches and type construction to be documented, formalized and discussed in my yet unpublished paper "Mappings between enumerated type domains for constructors and pattern matching".
