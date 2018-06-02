#### Blocks

The syntax clashes with the compound declaration, and a compound
statement. Might use either a 'block' keyword or use 'macro' instead
```
 template CodeTemplate(I:int) block {
   x:int = I
 }
```
or
```
 macro CodeTemplate(I:int) {
   x:int = I
 }
```
#### Compound
```
 template TemplateT(Signature T) {
   class A : T {
     ...
   }
   class B {
     ... T ...
   }
 }
```

### Template Inheritance

Not sure about this, normal template composition of sub templates maybe more powerful and versitile without the added complexity.

### Template Template Parameters
```
 template aTemplate(t:template) {
   ...(t)...
 }
```
