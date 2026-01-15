---
title: data registers
layout: home
parent: registers
nav_order: 6
---

# Data registers
The Motorola 68000 has 8 data registers, starting from `d0`, ending with `d7`. Each can store one longword worth of space. They are used for storing and changing numbers with math.

```
move.w    #$084D,d0  ; "d0" contains "0000084D"
add.b     #$17,d0    ; "d0" contains "00000864"
```
