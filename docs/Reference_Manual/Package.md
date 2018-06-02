Packages
--------

packages are a type of unit and inherit from them within the
infrastructure.

packages may package modules and other packages.
```
 package aPackage {
   include module aModule;
   include module anotherModule;
   include package aPackage;
 }
```
### Executable

packages may be used to describe executables.
```
 executable [windows|win32|win64|linux] aName Main.Main {
   class Main {
     method main();
       ...
     }
   ...
 }
```
### Libraries

static and dynamic standalone libraries are also packages. Normal
included libraries are modules though.
```
 library `<static dynamic>` [windows|win32|win64|linux] aLibrary {
   ...
 }
```
#### Windows

This is a sketch ...
```
 module windows {
   import extern "C" (WIN32, WIN32_LEAN_AND_MEAN) "windows.h"
   
   unit dll = library dynamic windows
 }
```
```
 module windows++ (...) {
   import extern "C++" (...) "windows.h"
   
   unit dll = library dynamic windows {
     requires function DllMain( HINSTANCE hDllHandle, DWORD nReason, LPVOID Reserved) : BOOL
   }
 }
```

Windows DLL usage :-
```
 import windows
 
 dll aDll {
   function DllMain( HINSTANCE hDllHandle, DWORD nReason, LPVOID Reserved) : BOOL {
     ....
   }
   ...
 }
```
Windows executable
```
 import windows
 
 executable windows anExecutable {
   function WinMain(
     in hInstance : HINSTANCE,
     in hPrevInstance : HINSTANCE,
     in lpCmdLine : LPSTR,
     in nCmdShow : int
   ) : int {
     ....
   }
 }
```

##Syntax


##Semantics
