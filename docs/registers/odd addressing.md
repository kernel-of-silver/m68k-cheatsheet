---
title: odd addressing
layout: home
parent: registers
nav_order: 8
---

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
		move.b    (a0),d0 ; invalid since you can't do byte size on address registers lol

		or.b      #$80,$FFFE00 ; valid
