---
date: 2021-03-21T14:41
tags:
  - haskell/library/brick
  - ui
  - tui
---

# Brick
[Brick](https://github.com/jtdaugherty/brick) is a library that allows you to write TUI in a simple way. Currently I'm writing this page according to brick v0.60.1.

The library start from App:

```haskell
data App s e n =
  App { appDraw         :: s -> [Widget n]
      , appChooseCursor :: s -> [CursorLocation n] -> Maybe (CursorLocation n)
      , appHandleEvent  :: s -> BrickEvent n e -> EventM n (Next s)
      , appStartEvent   :: s -> EventM n s
      , appAttrMap      :: s -> AttrMap
      }
```

where:

* s → application state;
* e → event type;
* n → resource name type;

#### appDraw
Function that takes the state and produce a list of [[brick-widget]]#. A widget is a description of how an element will be rendered to the screen. This function is called in two possible scenarios:

* at the start of the application;
* after an event;

Drawing functions files: `Brick.Widgets.Core` and `Brick.Widgets`

#### appHandleEvent
Function that handles event. Takes current app state, resource name type and the triggered event. `Next s` function returned describe what should happen after the event handler is finished. Three alternatives are:

* continue
* halt
* suspendAndResume

All is wrapped inside monad transformer with `IO Monad`, this allows user to call `lifIO`.

Several Widgets offer event handler monads that can be used by the user to generate some custom event.

#### appChooseCursor
Every [[brick-widget]]# rendered "has" a cursor, the real cursor that is printed on the screen is only one. With appChooseCursor user can choose which they want to use. Three most common cases are:

* neverShowCursor
* showFirstCursor → always show the first cursor request given
* showCursorNamed → show the cursor with the specified resource name

#### appAttrMap
This Map is used to simply the attributes associated with a [[brick-widget]]#. Instead of giving them to the drawing function, attributes are saved in a map indexed by the name. In this way is increased the modularity and there is the possibility so simply change attributes at runtime without any change inside drawing functions.
