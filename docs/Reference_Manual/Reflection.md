Reflection
----------

Modules maybe accessed as a DOM via compiletime and runtime reflection:-

`  module aModule = module["aModule"]`

`  constructor aConstructor = module["aModule"].class["aClass"].constructor["aConstructor"]`

Or by access notation

`  aModule.aConstructor(...)`

`  aModule.aClass.aConstructor(...)`

### Object and class based reflection

The following gives access to all the methods in an object as an
associative array :-

`  var methods = self.method`

The following gives access to a specific method :-

`  self.method["aMethod"]`

`  var methodName:string = "aMethod"`

`  var aMethod:method = self[method methodName]`

`  var anotherMethod:method = self[method methodName(int)]`

Access to all static methods in an object :-

`  self.method[static]`

Access to all static methods via the class :-

`  Self.method[static]`

##Syntax


##Semantics
