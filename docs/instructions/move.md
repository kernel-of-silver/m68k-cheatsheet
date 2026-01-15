---
title: move
layout: home
parent: instructions
nav_order: 101
---

`move` - Copy data from source to destination.

```
move.l    #$FFFF0000,$00001000  ; "$00001000" contains "FFFF0000"
move.w    #$EEEE,$00001002      ; "$00001000" contains "FFFFEEEE"
move.b    #$CC,$00001003        ; "$00001000" contains "FFFFEECC"
```
