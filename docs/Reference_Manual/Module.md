# Modules

Modules allow libaries or language extensions to be modularized. Modules may be imported or inherited.

`  import "aModule.module"`

is equivalent to :-

`  import aModule`

Modules maybe parameterized.
```
 module lazy( explicit : enum { implicit, explicit} = explicit) {
   ....
 }
```
Modules maybe accessed as a DOM via compiletime and runtime reflection:-

`  module aModule = module["aModule"]`

`  constructor aConstructor = module["aModule"].class["aClass"].constructor["aConstructor"]`

Or by access notation

`  aModule.aConstructor(...)`

`  aModule.aClass.aConstructor(...)`

# Syntax

# Semantics
