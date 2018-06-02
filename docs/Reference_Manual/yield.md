yield
-----
Illustrative code showing the power of yeild in transversing tree structures.

### Top Down, Left to Right
```
 iterator topdown_leftright(ref T : any) {
   for t in T {
     yield t
     topdown_leftright(t)
   }
 }
```
### Bottom Up, Left to Right
```
 iterator bottomup_leftright(ref T : any) {
   for t in T {
     bottomup_leftright(t)
     yield t
   }
 }
```
This mechanism is from Dr. Adrian D. Thurston's Thesis for the Colm programming language.

##References
[https://www.colm.net/files/colm/thurston-phdthesis.pdf](https://www.colm.net/files/colm/thurston-phdthesis.pdf)
