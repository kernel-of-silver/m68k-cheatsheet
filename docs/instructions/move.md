---
title: move
layout: home
parent: instructions
nav_order: 101
---

move - Copy data from source to destination.
```
move.b    #$95,$00001000
```
if "d0" started with "FFFF0000", it will now have "FFFF0095".

When the destination operand is an address register, you should use the `movea` instruction.
```
movea.l    $00FFFE02,a0
```
(You may not have to do this depending on how your assembler works.)
