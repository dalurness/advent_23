# Day 3: Elf Assembly Line

On a particular day at the North Pole, the elves are running an assembly line packaging presents. Each present is assigned a code upon completion that contains a sequence of instructions for how to assemble it. However, there seems to be a problem with the printer, and now, many presents have invalid sequences!

For each present, its assembly code consists of a string with the following commands: "A" for "Add part", "R" for "Remove part", "C" for "Check assembly", and "P" for "Package present".

Now, an assembly code is considered valid if there is a sequence of "A" and "R" commands leading to a correctly assembled present, followed by one single "C", and ending in "P". If there are multiple "C" commands, then the code is invalid, as the elves should only check the assembly once. Also, there cannot be an "R" without a corresponding "A" before it (as the elves can't remove a part they haven't added).

For example, the assembly code "AACP" is valid (add two parts, check, and then package), while "RCP" (removal without corresponding addition) or "ACCP" (two checks) is not.

Your task is to write a function that receives a list of assembly codes and returns the number of valid codes.

Example input:
```
ACP
CRARACP
ARAAACP
ARAPCP
AARRACP
ACR
ARCAP
ARACP
ARACP
ARCP
```

Example output (number of valid codes):
```
6
```

The elves want to get to the bottom of this and to start they need to know how many assembly codes are still valid. Count how many are complete and ready to be packaged.

## Part 2

After a while, and thanks to you for getting how many presents have a correct code, the elves figure out what is wrong with the printer. The assembly commands are getting mixed up when printing. The "A" and "C" commands sometimes get swapped and the "R" and the "P" commands can get swapped. So codes that have a "C" command anywhere else but as the second to last command are actually "A" commands, and codes that have a "P" command anywhere else but at the end are actually a "R" code.

The elves want to know how many parts were added and removed in total. After fixing the assembly codes count all the parts added and removed and report that back to the elves.
