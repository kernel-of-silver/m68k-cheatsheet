---
title: syntax
layout: home
nav_order: 2
---

# Syntax

Most of the time, 68000 instructions will be formatted in this manner:
- Command: Self-explanatory, what to do.
- Size: `.b` for byte (`F0`), `.w` for word (`F0F0`), `.l` for longword (`F0F0F0F0`)
- Source operand: The value to use or read from.
- Destination operand: The value that is being manipulated.

All of this comes together to make an instruction that reads like this:
```
move.w    #$F1A1,$0010FFAF
```
`move` is the command, `.w` is the size, `#$F1A1` is the source operand, and `$0010FFAF` is the destination operand.

There are some exceptions, the `swap` command does not use size or a source operand.
```
swap    d0
```

Numbers that start with `$` are intepreted as memory addresses or offsets. Numbers that start with `#` are intepreted as immediate numbers.

Immediate numbers are interpreted as decimal by default, adding `$` infront of `#` will interpret the immediate number as hexadecimal. (e.g. `#$20` is equal to `#32`) Adding `%` instead interprets it as binary. (e.g. `#%00100000` is equal to `#32`)
