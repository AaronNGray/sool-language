Examples
--------

### Coordinates
```
 opaque type angle = real
 
 abstract class coordinate {
   angle : angle {
     get() : angle
     set(angle)
   }
   radius : real {
     get() : real
     set(real)
   }
   x : real {
     get() : real
     set(real)
   }
   y : real {
     get() : real
     set(real)
   }
 }
  
 class cartesian inherits coordinate {
   constructor (x = 0, y = 0) instantiate;
   constructor polar(a:angle, radius:real);
   implicit constructor polar(p:polar);
   
   angle : angle {
     get() : angle = math.atan2(y/x)
     no set(angle)
   }
   radius : real {
     get() : real = (x^2*y^2)^0.5
     set(real)
   }
 
 protected:
   var x:real;
   var y:real;
 }
 
 class polar inherits coordinate {
   constructor (a:angle, radius:real) instatiate;
   constructor cartesian(x:real, y:real);
   implicit constructor cartesian(c:cartesian);
   
   x : real {
     get() : real
     set(real)
   }
   y : real {
     get() : real
     set(real)
   }
 
 protected:
   var angle:angle
   var radius:real;
 }
```
