---
title: not
layout: home
parent: instructions
nav_order: 107
---

`not` - Invert bits in destination operand.

```
move.l    #$FF8877FF,$00004800  ; "$00004800" contains "FF8877FF"
                                ; "FF8877FF" in binary is
                                ; "1111 1111 1000 1000 0111 0111 1111 1111"

not.l     $00004800             ; "$00004800" contains "00778800"
                                ; "00778800" in binary is
                                ; "0000 0000 0111 0111 1000 1000 0000 0000"

not.w     $00004802             ; "$00004800" contains "007777FF"
not.b     $00004803             ; "$00004800" contains "00777700"
```

This only works on data registers, not address registers.
