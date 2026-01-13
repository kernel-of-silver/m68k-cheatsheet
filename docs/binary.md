---
title: binary
layout: home
nav_order: 3
---

# binary and sizes

all data is made up of binary, which is made up of bits.
a bit can be a 0 or a 1, representing off or on, false or true.
nybbles contain 4 bits, bytes contain 8 bits, words contain 16 bits,
and longwords contain 32 bits.
you can visualize it like this:

size        binary                                     hex
bit         0                                          0
nybble      0010                                       2
byte        0010 1100                                  2C
word        0010 1100 1111 0101                        2CF5
longword    0010 1100 1111 0101 1001 1101 0111 0110    2CF5 9D76

every hex character is also represented by a different nybble, like this:

binary    hex
0000      0
0001      1
0010      2
0011      3
0100      4
0101      5
0110      6
0111      7
1000      8
1001      9
1010      A
1011      B
1100      C
1101      D
1110      E
1111      F

also worth keeping in mind, the right-most bit (0001) is the least significant
bit, whereas the left-most bit (1000) is the most significant bit.

this info is necessary for some instructions, like "not" and "and".
