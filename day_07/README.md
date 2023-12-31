# Advent of Code Day_07 

A large amount of planning goes into Santa's trek every year. There is a common misconception that his sleigh flies as high as he wants it to, but that is simply not true. The higher he gets in the air, the thinner the air is, and the reindeer begin to have trouble getting enough oxygen to produce the lift that Santa's sleigh requires. 
 
Creating Santa's travel plans takes a great deal of effort, and Buddy (lead elf over sleigh maintenance and travel) needs you to help out mapping the path from Salt Lake to Denver. The terrain was measured using a tool called a PathFinder that checks the topography at the specific altitude that Santa is planned to be flying at. The Rocky Mountains are very tall, so a path through the canyons will need to be discovered. 

**Problem**: Included is a file that contains the map of the area output by the PathFinder. The map shows mountains as "**X**"'s and open air as "**O**"'s (letter). We went ahead and marked Santa's planned positioning at the start of your leg of the journey with an "**S**", and the location we want him to be leaving your leg of the journey as "**E**". How he gets there is up to you. Each letter correlates to about 5 square miles, so the output of the program will be the distance Santa needs to go a direction, and the direction(first letter of the direction). The map is laid out such that the top of the map is North, the bottom is South, to the right is East, and to the left is West.

**Example**:
Given the map:
```
OOOOOOOOOOOOOOOOOOOOOOOOOOOO
OOOOOOOOOOOOXXXXXOOOOOOOOOOO
SOOOOOXXXXXXXXXXXOOOOOOOOOOO
OOOOOOOXXXXXXXXOOOOOOOOOOOOO
OOOOOOOOOOXXXXOOOOOOOOOOOOOO
OOOOOOOOOOOOOOOOXXXXOOOOOOOE
OOOOXXXOOOOOOOOOOOXXXXOOOOOO
OOXXXXXXOOOOOOOOOOOOOOOOOOOO
```
A Valid Solution would be:
```
2N28E5S
```
Which describes the path:
```
|---------------------------
|OOOOOOOOOOOXXXXXOOOOOOOOOO|
SOOOOOXXXXXXXXXXXOOOOOOOOOO|
OOOOOOOXXXXXXXXOOOOOOOOOOOO|
OOOOOOOOOOXXXXOOOOOOOOOOOOO|
OOOOOOOOOOOOOOOOXXXXOOOOOOOE
OOOOXXXOOOOOOOOOOOXXXXOOOOOO
OOXXXXXXOOOOOOOOOOOOOOOOOOOO
```

**Challenge**:
Find the optimal path for Santa to go!

**Notes**:
Use any language you like. Post/link results and source code in channel (feel free to add comments and/or ask for help). If you post the answer, you can "hide" it in discord by having two "pipes" on either side.
Ex: ```||Result||```

