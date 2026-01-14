---
title: clr
layout: home
parent: instructions
nav_order: 106
---

clr - clear destination

		clr.b    $FFFD02

if "FFFD02" contains "EF", it will now have "00".
this just zeroes out a destination operand. this works with word and longword
sizes like you'd expect. data registers work too.

		clr.w    d0

however, this won't work with address registers.
