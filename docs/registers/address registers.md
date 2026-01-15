---
title: address registers
layout: home
parent: registers
nav_order: 7
---

# Address registers
The Motorola 68000 has 8 address registers, starting from `a0`, ending with `a7`. Each can store one longword worth of space. Address registers are only meant to store memory addresses, and can only have word and longword instructions performed on them.

As a result, some instructions that work with data registers do not work with address registers.

```
move.l    $#00FFFE02,a0  ; "a0" contains "00FFFE02"
```

Putting an address register in brackets will use the stored memory address that the address register contains , rather than replacing the data in it.

```
move.w    #$084D,a0  ; "a0" contains "0000084D"
move.b    #$44,(a0)  ; "$0000084D" contains "44"
```
