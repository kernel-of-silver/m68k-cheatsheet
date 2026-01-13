---
title: syntax
layout: home
nav_order: 2
---

# syntax

most of the time, 68000 instructions will be formatted in this manner:
- command: self-explanatory, what to do
- size: .b for byte (F0), .w for word (F0F0), .l for longword (F0F0F0F0)
- source operand: the value to use or read from
- destination operand: the value that is being manipulated
all of this comes together to make an instruction that reads like this:

		move.w    #$F1A1,$0010FFAF

`move` is the command, `.w` is the size, `#$F1A1` is the source operand, and
`$0010FFAF` is the destination operand.
some exceptions, `swap` command does not use size or a source operand.

		swap    d0

numbers that start with $ are intepreted as memory addresses or offsets.
numbers that start with # are intepreted as immediate numbers.
immediate numbers are interpreted as decimal by default,
adding $ infront of the # will interpret it as hexadecimal. (e.g. #$20 is #32)
adding % instead interprets it as binary. (e.g. #%00100000 is #32)