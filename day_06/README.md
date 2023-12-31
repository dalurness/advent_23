# Day 6: Balancing Tree Act

As the elves are busy making Christmas trees Mrs. Santa comes to look over the finished products. She notices that some of the Christmas trees are leaning one way or the other while some are straight as an arrow. She consults with the Head Elf and confirms that there is an issue in the production of Christmas trees. Help them figure out which trees are off balance so they know how much material is going to need to be recycled.

The elves today were making simple trees with only 2 branches and up to 2 ornaments on each branch. Each part of the tree has a specific weight.
- The trunk
- Each branch (just the bare branch, before it was decorated)
- Each ornament

_Mrs. Santa has noted that the trees only start to lean over if the branches weights are off by more than 1._

The trees are given as input in the following format:

```
9
6 6
1 2 2 1

8
4 5
2 2 2 2

9
5 6
1 2 2 2

8
6 6
2 2 _ _
```

Each tree is separated by a blank line. Each tree is defined as such:
- The first line is the weight of the tree trunk
- The next line has the weight of the left branch and the right branch, in that order
- The last line has the weights of the ornaments. The first two are for the left branch, the last two are for the right branch.
  - If there is an underscore `_` it means there is a missing ornament so don't count it

Calculate the total weight of all the trees that are off balance. For the example above the total weight of off balance trees (the last 2) is 51.
