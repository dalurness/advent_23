# Day 10: A Sorting Disaster! 

Christmas Eve is all about efficiency. In order for Santa to be able to deliver so many presents, Elves put a lot of preliminary work into mapping efficient routes and having the right presents available at the right time. Presents are placed into a specific order that is indicated by a removeable number label. These numbers are placed into the bag in order, from the largest number being deepest in the bag, to smallest number being at the top of the bag. Unfortunately, one of the bags of presents was dropped while being moved to the Present Staging Area.

**Problem**: In order to get things going again, we need to get all of the presents back into order, as well as make sure that no presents are missing! Luckily, the last several presents were unaffected (as the bag was tipped over, not dumped out). Return 2 lists. The first contains the first number (always 0), the median (middle number), and the last number. The second list contains all of the presents, if any, that are missing (sorted).

**Example**:
```
[0,1,3,5,7,9,2,4,8,9]
0 1 2 3 4 5 7 8 9
```
Should return
```
[0,4,9]
[6]
```