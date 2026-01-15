---
title: add
layout: home
parent: instructions
nav_order: 102
---

`add` - Add data from source to destination.

```
move.l    #$FFFF0095,d0  ; "d0" contains "FFFF0095"
add.b     #$08,d0        ; "d0" contains "FFFF009D"

move.l    #$1234FFFF,d0  ; "d0" contains "1234FFFF"
add.b     #$08,d0        ; "d0" contains "1234FF07"
```
