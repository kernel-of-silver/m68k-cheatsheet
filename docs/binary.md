---
title: binary
layout: home
nav_order: 3
---

# binary and sizes

All memory can be reduced down to bits. A bit is either a 0 or a 1, off or on, false or true. You usually work with larger sizes though.

Nybbles contain 4 bits, bytes contain 8 bits, words contain 16 bits, and longwords contain 32 bits. It can be visualized like this:
| size     | binary                                  | hex       |
|:---------|:----------------------------------------|:----------|
| bit      | 0                                       | 0         |
| nybble   | 0010                                    | 2         |
| byte     | 0010 1100                               | 2C        |
| word     | 0010 1100 1111 0101                     | 2CF5      |
| longword | 0010 1100 1111 0101 1001 1101 0111 0110 | 2CF5 9D76 |

Every hex character can also be represented by a nybble:
| binary | hex |
|:-------|:----|
| 0000   | 0   |
| 0001   | 1   |
| 0010   | 2   |
| 0011   | 3   |
| 0100   | 4   |
| 0101   | 5   |
| 0110   | 6   |
| 0111   | 7   |
| 1000   | 8   |
| 1001   | 9   |
| 1010   | A   |
| 1011   | B   |
| 1100   | C   |
| 1101   | D   |
| 1110   | E   |
| 1111   | F   |

Also worth keeping in mind is bit significance. The right-most bit (`0001`) is considered the least significant bit, whereas the left-most bit (`1000`) is the most significant bit.

This info is necessary for some instructions, like `not` and `and`, which work with binary.
