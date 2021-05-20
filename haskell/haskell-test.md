---
date: 2021-03-21T14:41
tags:
  - haskell/test
  - haskell/howto
---

# Test
There are multiple types of tests and severals libraries in haskell implement them: 

* *Property Test* →  A property of a program is an observation that we expect to hold true regardless of the program’s inputs. It may involve only the output (“always outputs a positive number”) or compare input and output (“preserves list length”) or even assess external effects (“matches the output of a trusted external program”). Property test libraries are [[QuickCheck]]# and SmallCheck
* Specs test → Specifications test library is [[Hspec]]#
