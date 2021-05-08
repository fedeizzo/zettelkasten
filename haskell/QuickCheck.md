---
date: 2021-03-21T14:41
tags:
  - haskell/test/quick-check
---

# QuickCheck
QuicCheck is used to make property test.

It creates a specific amount of random inputs, then they are used in order to test functions.

## Gen
User can use primitive API in order to build complex random data input.

```haskell
-- Random between a specific range
choose :: Random a => (a, a) -> Gen a

-- Pick elements at random position from non empty list
elments :: [a] -> Gen a

-- Pick a Gen from a Gen list
oneOf :: [Gen a] -> Gen a

-- Pick a Gen from a Gen list with a specifified distribution
frequency :: [(Int, Gen a)] -> Gen a

-- Use Gen with a specific random range
sized :: (Int -> Gen a) -> Gen a
```

After receive `Gen a` type user must use *IO Monad* to consume it:

```haskell
generate :: Gen a -> IO a
-- example
generate $ elements [1, 2 ,3]
```

## Arbitrary
Arbitrary are used to produce generators for more complex data type. Arbitrary does not force any law like other typeclasses in haskell. They could be used as normal `Gen`:

```haskell
class Arbitrary a where
  arbitrary :: Gen a

-- Manually generating random Bool
generate $ choose (False, True)

-- Using instance of Arbitrary
generate (arbitrary :: Gen Bool)
```

Arbitrary can also be used in a nested way, this allows to build more complex types:

```haskell
generate (arbitrary :: Gen [(Int, Bool)])
```

## Result
A property can be expressed as a `Gen Result`, *Result* can be used to display informations directly to the user (result, stats, etc.). *Result* can be used to test laws:

```haskell
-- succeded :: Result
-- failed :: Result
commutative-law :: Gen Result
commutative-law = do
  (x, y) <- arbitrary :: Gen (Int, Int)
  return $ if x + y == y + x
    then succeded
    else failes { reason = "Failed for some reason" }
```

In order to simply this process `Testable` class can be used:

```haskell
(Arbitrary a, Show a, Testable prop) => Testable (a -> prop)

commutative-law :: Int -> Int -> Bool
commutative-law x y = x + y == y + x
```

In this case any `Arbitrary` instances can be used automatically in `Testable` context. After that to test:

```haskell
quickCheck :: Testable prop => prop -> IO ()
quickCheck commuative-law
```

## Run tests
