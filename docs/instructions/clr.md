---
title: clr
layout: home
parent: instructions
nav_order: 106
---

`clr` - Clear destination operand.

```
move.l    #$EE1234AA,$00FFFD00  ; "$00FFFD00" contains "EE1234AA"
clr.b     $00FFFD03             ; "$00FFFD00" contains "EE123400"
clr.w     $00FFFD02             ; "$00FFFD00" contains "EE120000"
clr.l     $00FFFD00             ; "$00FFFD00" contains "00000000"
```

This only works on data registers, not address registers.
