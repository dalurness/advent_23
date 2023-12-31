# Day 21: Fix the Schedule

Santa has an incredibly busy schedule, managing the toy workshop, checking the naughty or nice list twice, and then delivering the presents around the world. To ensure efficiency, the elves keep a meticulous record of Santa's appointments.

Last year, due to some absentmindednes, Santa ended up with some double-booked appointments, meaning that two or more events were scheduled to occur at the same exact time. Now with a new year approaching, Santa wants to avoid the same scheduling conflicts.

Your task is to write a program that will receive a list of Santa’s appointments from last year. Each appointment consists of a start time and an end time (inclusive to exclusive: the start time is included in the schedule while the end time is the minute the next event can start). You are to find and return the total number of minutes that were double booked so Santa can see how much time he might've wasted.


Example:
```
07:42-08:26 Enjoy a festive breakfast seasoned with cinnamon and nutmeg
08:23-09:11 Meet with the Department of Naughty or Nice Delivery to finalize routes
```

That overlaps by 3 minutes (8:23, 8:24, and 8:25).
