---
date: 2020-12-09T14:57
tags:
  - zettel-syntax
---

# Link queries
Link queries are very powerful feature that allow you to make dynamically links.

### Tags
```
[[z:zettels?tag=tagName]]
```

### Tags pattern
At tagName level
```
[[z:zettels?tag=tagName/*]]
```

Recursively after tagName
```
[[z:zettels?tag=tagName/**]]
```

### Control flags
There are some control flags that can be added at the end of the tag:

* grouped → group result by matching tag
* timeline → sort results by date contained into [[metadata]]
* showid → show zettel id
* limit → limit amount of zettels shown by the query

*Usage examples*:

* `[[z:zettels?tag=**&limit=2&timeline]]`
* `[[z:zettels?tag=**&timeline&grouped]]`
