---
title: sub
layout: home
parent: instructions
nav_order: 103
---

`sub` - Subtract data from source to destination.

```
move.l    #$FFFF0095,d0  ; "d0" contains "FFFF0095"
sub.b     #$08,d0        ; "d0" contains "FFFF008D"

move.l    #$12340000,d0  ; "d0" contains "12340000"
sub.b     #$08,d0        ; "d0" contains "123400F8"
```
