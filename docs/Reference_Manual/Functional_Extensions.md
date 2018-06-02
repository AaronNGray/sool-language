functional module
-----------------

`import functional`

This gives an "-\>" operator and functions like "map", "foldl", and
"foldr", etc...

lazy module
-----------

To make code implicitly lazy :-

`import lazy(implicit)`

`module lazy( explicit : enum { implicit, explicit} = explicit) inherit functional {`
`    ...`
`}`

To allow marked up lazy code :-

`import lazy(explicit)`

`lazy function f() { ... }`

Lazyness will be explicit by default.

`import lazy`

curry module
------------

To have implicit currying :-

`import curry(implicit)`

For explicit currying :-

`import curry(explicit)`

`curried function f((:a):b):c`

Or :-

`function f: a -> b -> c`

`f = curry g`

`g = uncurry f`

`f : (:a, :b):c`

`g : ((:a):b):c`

Currying will be implicit by default.

`f : function (:a, :b) : c`

`g : function ( function (:a) : b) ) : c`
