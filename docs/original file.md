---
title: original file
layout: home
nav_order: 999
---

This is the original file that I've been writing to before moving onto this website. Beware that this is probably a bit incoherent or outright incorrect.

The pages on this website are more coherent, better written, have more necessary info than this file.

```
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



# registers
the 68k has 8 data registers, starting from d0, ending with d7. each can store  
one longword worth of space. they are used for storing and changing numbers
with math.

		; "d0" will now contain the longword "0000084D"
		move.w    #$084D,d0
		; this adds "#$17" to "d0", and "d0" will now contain "00000864"
		addi.b    #$17,d0

there are also 8 address registers, starting from a0, ending with a7. they can
also store one longword worth of space.
the main difference is that address registers only store memory addresses,
and can only have word and longword instructions performed on them. also, some
instructions that work with data registers do not work with address registers.

		movea.l    $00FFFE02,a0

putting the address registers in brackets will use the stored memory address
that the address register contains, rather than replacing it.

		move.b    #$44,(a0)





# instructions

move - copy data from source to destination

		move.b    #$95,$00001000
		
if "d0" started with "FFFF0000", it will now have "FFFF0095".

when copying data into an address register, you use the instruction "movea".

		movea.l    $00FFFE02,a0



add - add data from source to destination

		add.b    $00090024,d0

assume $00090024 contains "08".
if "d0" started with "FFFF0095", it will now have "FFFF009D".
if "d0" started with "1234FFFF", it will now have "1234FF07".

note how only the byte furthest to the right is modified. same applies to word.

also, when the source operand is an immediate number, you must use the "addi"
instruction, which is short for "add immediate."

		addi.b    #$08,d0

some assemblers will not be super strict and will accept "add" instead.



sub - subtract data from source to destination

		sub.b    $00090024,d0

assume $00090024 contains "08".
if "d0" started with "FFFF0095", it will now have "FFFF008D".
self-explanatory, works like add. "subi" exists for "subtract immediate" too.



swap – swap register words

		swap    d0
	
if "d0" started with "FFFF0095", it will now have "0095FFFF".
this only works on data registers, not address registers.



exg – exchange registers

		exg.l    d0,d1

if "d0" has "FFFF0095", and d1 has "DEADBEEF",
"d0" will now contain what "d1" has, and vice versa with "d1".
this works on address registers too.
this only works with longword, word and byte exchange don't work.



clr - clear destination

		clr.b    $FFFD02

if "FFFD02" contains "EF", it will now have "00".
this just zeroes out a destination operand. this works with word and longword
sizes like you'd expect. data registers work too.

		clr.w    d0

however, this won't work with address registers.


# odd addressing
when using word or longword sizes, you cannot use use an address that is an
odd number. attempting to do so will crash the 68k with an "address error."
this is due to a design quirk of the 68k CPU.
it also applies to all instructions.

		move.w    $FFFE00,d2 ; valid
		move.w    $FFFE01,d2 ; invalid

		movea.l   #$00FFFE00,a0
		move.w    (a0),d0 ; valid
		movea.l   #$00FFFE01,a0
		move.w    (a0),d0 ; invalid
		
		or.w      #$8080,$FFFE00 ; still valid
		or.w      #$8080,$FFFE01 ; still invalid...

you *can* access odd addresses with a byte size though.

		move.b    $FFFE01,d2 ; valid

		movea.l   #$00FFFE01,a0
		move.b    (a0),d0
	; above is invalid since you can't do byte size on address registers lol

		or.b      #$80,$FFFE00 ; valid
```
