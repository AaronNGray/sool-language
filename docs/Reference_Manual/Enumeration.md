## enum ##
enumerations may be typed, and inherit a type to use, and compacted to a number of bits if "Platform" is imported, thus :-

`   enum color : bit[2] { Black, Red, Green, Blue }`

**enum**'s maybe opaque or transparent, requiring qualification or not

### opaque ###
**enum**'s are opaque by default.
```
  opaque enum Action { Shift, Reduce, Accept, Error }
  var action : Action = Action::Shift
```
### transparent ###
**transparent** **enum**'s register their members in the parents namespace.
```
  transparent enum Action { Shift, Reduce, Accept, Error }
  var action : Action = Shift
```
