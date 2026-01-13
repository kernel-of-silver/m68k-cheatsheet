---
title: data registers
parent: registers
nav_order: 5
---

# registers
the 68k has 8 data registers, starting from d0, ending with d7. each can store  
one longword worth of space. they are used for storing and changing numbers
with math.

		; "d0" will now contain the longword "0000084D"
		move.w    #$084D,d0
		; this adds "#$17" to "d0", and "d0" will now contain "00000864"
		addi.b    #$17,d0