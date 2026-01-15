---
title: swap
layout: home
parent: instructions
nav_order: 104
---

`swap` – Swap register halves.

```
move.l    #$1234FFFF,d0  ; "d0" contains "1234FFFF"
swap      d0             ; "d0" contains "FFFF1234"
```

This only works on data registers, not address registers.
