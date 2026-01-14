---
title: exg
layout: home
parent: instructions
nav_order: 105
---

exg – exchange registers

		exg.l    d0,d1

if "d0" has "FFFF0095", and d1 has "DEADBEEF",
"d0" will now contain what "d1" has, and vice versa with "d1".
this works on address registers too.
this only works with longword, word and byte exchange don't work.
