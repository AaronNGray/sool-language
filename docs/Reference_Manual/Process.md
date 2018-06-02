### process

`   import platform.process`
`   import Table`
`   `
`   process Philosopher {`
`   protected:`
`       Table:ref Table`
`       Position:Table.Position`
`       LeftFork:bool`
`       RightFolk:bool`
`   public:`
`       message getLeftFork():bool {...}`
`       message getRightFork():bool {...}`
`   }`
`   `
`   unittest {`
`       philosopher1:Philosopher`
`       if (send philosopher1.getLeftFolk())`
`           echo "philosopher1 picked up left folk\"`
`       else`
`           echo "philosopher1 cannot pick up left folk\"`
`   `
`       if (balk philosopher1.getLeftFolk())`
`           echo "philosopher1 picked up left folk\"`
`   }`

### parallel

`   parallel {`
`       test1()`
`       test2()`
`   }`

### program

`   import platform.program`

`   program HelloWorld {`
`       main() { echo "Hello World !!!"; }`
`   };`

Definition of program as a stereotype

`   stereotype class Program : public Process, public Module {`
`       void echo(string);`
`       void exit(int);`
`       void main(args:string[],env:[map]);`
`       const int stdin = 0;`
`       const int stdout = 1;`
`       const int stderr = 2;`
`   };`

### interrupt

`   class aDevice : public Device {`
`   public:`
`       interrupt anInterrupt() { ... }`
`   };`

### mutex

### spinlock

### monitor

### sync

### async

### lock

Syntax
------

Semantics
---------