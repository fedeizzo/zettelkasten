---
date: 2020-12-09T15:06
tags:
  - zettel-syntax
---

# Metadata
Metadata must stay at the top of the file inside `---` as shown below:
```
---
metadata
---
```

### Date
```
date: 2020-01-01T13:24
```

### Slug
Name displayed during html render instead the zettle title
```
slug: name
```

### Pinning
A special tag can be used in order to pin at the top of the z-index
```
tags:
  - pinned
```

### Hiding
Is possible to hide a zettel
```
unlished: true
```
