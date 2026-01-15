---
title: exg
layout: home
parent: instructions
nav_order: 105
---

`exg` – Exchange registers.

```
move.l    #$1234FFFF,d0  ; "d0" contains "1234FFFF"
move.l    #$DEADBEEF,d1  ; "d1" contains "DEADBEEF"
exg.l     d0,d1          ; "d1" contains "1234FFFF", and "d0" contains "DEADBEEF"
```

This only works with longword, word and byte sizes don't work.
This works with data and address registers.
