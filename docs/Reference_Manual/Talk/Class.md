Should all nested classes be virtual ? As should all functions be
virtual ?

syntax and semantics of implicit constructors and converters are a bit
messy and need thinking through properly as they cross each others
domains.

extended classes could probably be done by inheritance and scope.

Syntax
------

### anonymous classes

`   `**`new`**` class-name `**`(`**` [ argument-list ] `**`)`**` `**`{`**` class-body `**`}`**

`   `**`new`**` interface-name `**`()`**` `**`{`**` class-body `**`}`**
