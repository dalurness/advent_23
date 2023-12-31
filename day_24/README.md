# Day 24: Elf Numbers

Santa and the elves are doing the last of the preparations getting ready to set off into the sky tonigh. As they get ready the ordering of the elves going through the halls is important to keep order and so nothing gets mixed up.

Elves use a system of numbering creatively called Elf Numbers. There is a formula mapping regular natural numbers to elf numbers. For each digit of a natural number put it through the following formula and add up all the results for each digit. Then repeat that process over and over again. If the sum is ever equal to 0 then the number is an Elf number. If the sum never reaches 0 then it is not an Elf Number.

The formula is:

```math
e(n) = \sum_{d \in \textup{digits of} n}^{}4d^{3}-20d^{2}+24d
```

Here's the first 10 numbers put through the formula once.

| $n$ | $e(n)$ |
|:---:|-------:|
|  0  |      0 |
|  1  |      8 |
|  2  |      0 |
|  3  |      0 |
|  4  |     32 |
|  5  |    120 |
|  6  |    288 |
|  7  |    560 |
|  8  |    960 |
|  9  |   1512 |

Taking 4 as an example through the full process:

```math
\begin{aligned}
e(4) &= 32 \\
e(32) = e(3) + e(2) &= 0 + 0 = 0
\end{aligned}
```

Taking 8 as an example through the full process:

```math
\begin{aligned}
e(8) &= 960 \\
e(960) = e(9) + e(6) + e(0) &= 1512 + 288 + 0 = 1800 \\
e(1800) = e(1) + e(8) + e(0) + e(0) &= 8 + 960 + 0 + 0 = 968 \\
e(968) = e(9) + e(6) + e(8) &= 1512 + 288 + 960 = 2760 \\
e(2760) = e(2) + e(7) + e(6) + e(0) &= 0 + 560 + 288 + 0 = 848 \\
e(848) = e(8) + e(4) + e(8) &= 960 + 32 + 960 = 1952 \\
e(1952) = e(1) + e(9) + e(5) + e(2) &= 8 + 1512 + 120 + 0 = 1640 \\
...
\end{aligned}
```

Therefore 4 is an Elf Number and 8 will never terminate so it is not an Elf Number.

It's imperative that Santa knows _the sum of the first 50,000 Elf Numbers_. Report back to Santa as soon as you get the results.

<details>
<summary>Hint</summary>
If there is a cycle in the chain when processing the numbers before reaching 0 then you know it won't be an Elf Number.
</details>
