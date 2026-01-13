---
title: address registers
layout: home
parent: registers
nav_order: 7
---

there are also 8 address registers, starting from a0, ending with a7. they can
also store one longword worth of space.
the main difference is that address registers only store memory addresses,
and can only have word and longword instructions performed on them. also, some
instructions that work with data registers do not work with address registers.

		movea.l    $00FFFE02,a0

putting the address registers in brackets will use the stored memory address
that the address register contains, rather than replacing it.

		move.b    #$44,(a0)