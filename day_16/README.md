# Day 16: Santa's Perfect Batch 
Santa is a celebrity to the elves. He is the big man. The man in charge. The team captain. The head honcho. The chief. Often elves will go out of their way to give him a sample of their work so that he can see what a great job they are doing.

A little known fact is that Santa LOVES Hershey's Kisses. A well known fact is that for whatever reason, the different wrapper colors of kisses always just taste a little different. It is very common for someone to pick a favorite, and eat all of the red-wrapped kisses, because those ones just taste the best. Santa, on the other hand, likes to take a different approach. Santa loves to try as many different colors as he can to really delve into the combination of all of the different flavors of Hershey's milk chocolate.

In the factory making the chocolates, the finished kisses are on a conveyor belt, being packaged by elves at the end of it. Some of the elves in the factory would like to present Santa with a perfect batch of chocolates, a batch that contains a mix of all of the different colors. However, the manager doesn't want there to be a bunch of gaps in the assembly line while they pick a bunch of different ones out. He has agreed to allow the elves to take one consecutive section of kisses for Santa's batch. That way the elves that are doing the packaging can clearly recognize the gap and take a little rest instead of being thrown out of their groove.

**Problem**: Attached is a file containing letters that represent the different colors of Hershey's kisses on the conveyor belt in order. We need you to figure out where in the line the first longest group of kisses are that are not the same color. Then print out the index of where the start and end kisses are so that we know how many to grab.

**Example**:
In the line of kisses:
```RGGBPRPGRBBRWOPRRPGRBRW```
The largest group of unique colors is:
<code>RGGBPRPGRB<b>BRWOP</b>RRPGRBRW</code>
So the indexes would be [10,14] to grab that group of kisses.