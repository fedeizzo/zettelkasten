---
date: 2021-03-21T14:41
tags:
  - haskell/library/brick
  - ui
  - tui
  - widget
---

# Widget
Widget describe how the image passed to vty is created.

## Rendering area
An important thing is the rendering area. The size can described through types inside `Brick.Types.Size`. Two values are:

* Fixed → always same amount of space
* Greedy → take how much space is given to the widget

Different policies can be set for columns and rows.

## Attribute map
The rendering context contain an attribute map used to lookup attribute.

## Border
Widgets can have borders. The style (unicode or ascii for example) can be set once per application. This is forced in order to maintain a single style through the entire process.
