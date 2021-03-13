---
date: 2020-12-06T21:05
---

# Syntax
Tutorial on github markdown can found here:

* [CommonMark](https://commonmark.org/)
* [GFM](https://github.github.com/gfm/)
* [[commonmarkExtension]]#[^conExt]

## Link
There are three types of links:

* __markdown link__ → `[text](link)`
* __zettel link__ → `[[zettelId]]`
* __zettel branching link__ → `[[zettelId]]#`

### Link queries
[[linkQueries]] are more powerful link options

## Highlight
==Highlight text== can be made with:
```
== text ==
```

## Tags
Tag can stay in [[metadata]] like this
```
---
tags:
  - tag1
  - tag2
---
```
or can be used putting a `#` before the tag during the text

### Metadata
[[metadata]]#


### Math
Math can be used in three ways:

* __inline__ → surround code with `$ code $`
* __block__ → surround code with `$$ code $$`
* __multiline block__:
```
$$
code
$$
```

### Custom styling
TODO enrich this part https://github.com/srid/neuron/issues/176

### Custom html/js
There is the possibility to [add custom html and js](https://neuron.zettel.page/custom-head.html) into the generated page. For now is a cool thing but I want something more natural and tedious

[^conExt]: [CommonMark extension](https://github.com/jgm/commonmark-hs/tree/master/commonmark-extensions) are some user developed extra functions included in neuron
