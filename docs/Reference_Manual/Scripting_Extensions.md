Scripting Extensions
--------------------

implicit or explict variable declarations
-----------------------------------------

`   module scripting( explicit : enum { implicit, explicit} = explicit) {`
`       ....`
`   }`

### getters, setters and other operators

`   class slots {`
`       slots : dictionary of dynamic`
`   `
`       operator get( string name) : dynamic {`
`           return object[name]`
`       }`
`       operator set( string name, dynamic value) {`
`           object[name] = value`
`       }`
`       operator unset(string name) {`
`           object[name] = undefined`
`       }`
`       operator undefined|isset(string name) : boolean {`
`           return object[name] == undefined`
`       }`
`       operator delete(string name) {`
`           delete object[name]`
`       }`
`       operator exists(string name) : boolean {`
`           return object[name] exists`
`       }`
`   }`

### exists

`   if exists x then y else z`

`   if x exists then y else z`

### delete

`   delete x`

### undefined

`   x = undefined`

`   if x is undefined then x else y`

`   if x == undefined then y else z`
