# Day 12: Compression Bells

The elves have a lot of paperwork to file every year so they came up with an algorithm to compress data to save on space.

The alorithm works by successively replacing a common string in a file with a single character. Repeating that process several times untile the file is smaller. In order to retrieve the original data back, they keep track of what substitutions were made at the top of the file.

At the beginning of the file there are lines showing what was replaced in order. There is a single character followed by ` => ` followed by a JSON encoded string. The character was used to substitute the string in the file. Then there is an empty line followed by the rest of the contents of file.

Decompress some of the elves' files to help them figure out what is in there.


Here's an example:

```
~ => " the "
} => "listen"
| => "I'm drea"
{ => "|ming of"
z => "{ a whit"
y => "ze Chris"
x => "ytmas\nJu"
v => "xst like"

v~ones I used to know
Where~treetops g} and children }
To hear sleigh bells in~snow
```

That decompresses to the following:

```
I'm dreaming of a white Christmas
Just like the ones I used to know
Where the treetops glisten and children listen
To hear sleigh bells in the snow
```
