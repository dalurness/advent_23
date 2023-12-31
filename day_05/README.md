# Day 05

Santa has a printer that he uses to create stocking stuffers. Sadly, all of the printers lost their rendering firmware! Luckily, the source files for the designs he prints are pretty simple.

For this challenge, create a renderer that uses the following rules:

- Each command is line separated
- There are two types of commands
    - Movement
        - `LR`: reset location to (0,0)
        - `D<num>`: move down a number of spaces
        - `U<num>`: move up
        - `R<num>`: move right
        - `L<num>`: move left
    - Paint
        - `P<char>`: Prints the char at the current location

Here is an example of how the canvas coordinate system works:

```
                    +X

       0   4   8
      ┌─────────────────>
     0│
      │
      │
      │
     4│
      │ ┼
      │   (1,5)
      │
+Y   8│
      │
      V
```

The canvas doesn't have explicit dimensions, but must be large enough to include all points.


Here's an example command file:

```
R1
P1
LR
D1
P2
R1
D1
P3
LR
R2
D1
P4
```

Should output:

```
 1
2 4
 3
```

**You will find numbered files (eg `1.txt`, etc), render them**. `0.txt` is small and may be a good starting point.
