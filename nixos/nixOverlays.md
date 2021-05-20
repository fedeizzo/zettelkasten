---
date: 2020-12-09T21:35
tags:
  - linux/nixos
  - overlays
  - nixos/bestpractice
---

# Overlays
An overlay is fancy way of `pacakgeOverride` and `overridePackages`. Is a best practice to use overlays over others techniques because overlays can be stacked together.

## Data flow
Data flow is like inheritance in OO languages:

![](./static/overlaysDataFlow.png)

`self` is shared between all states and `super` refers always to the nearest parent. 
