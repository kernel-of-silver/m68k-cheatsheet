---
title: sub
layout: home
parent: instructions
nav_order: 103
---

sub - subtract data from source to destination

		sub.b    $00090024,d0

assume $00090024 contains "08".
if "d0" started with "FFFF0095", it will now have "FFFF008D".
self-explanatory, works like add. "subi" exists for "subtract immediate" too.
