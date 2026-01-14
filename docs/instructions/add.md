---
title: add
layout: home
parent: instructions
nav_order: 102
---

add - add data from source to destination
```
add.b    $00090024,d0
```
Assume $00090024 contains "08".

if "d0" started with `FFFF0095`, it will now have `FFFF009D`.

if "d0" started with `1234FFFF`, it will now have `1234FF07`.

When the source operand is an immediate number, you must use the `addi`
instruction, which is short for "add immediate."
```
addi.b    #$08,d0
```
some assemblers will not be super strict and will accept "add" instead.
