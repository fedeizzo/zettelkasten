---
date: 2021-03-21T16:09
tags:
  - haskell/test/hspec
---

# Hspec
The two core tools offered by Hspec are `describe` and `it` as other languages libraries:

```haskell
main :: IO ()
main = hspec $ do
  describe "Prelude.read" do
    it "can parse integers" $ do
      read "10" `shouldBe` (10 :: Int)
    it "can parse floating-point numbers" $ do
      read "2.5" `shouldBe` (2.5 :: Float)
```

## Hooks
`before_` and `after_` can be used to perform some IO operation before a single test:

```haskell
main :: IO ()
main = hspec $ before_ doSomething $ do
  ...
```

`around_` instead perform IO operation between each spec.

There are another different types of hooks: `after` `before` `around`. These are without underscore. They can be used to pass argument directly to specs.

```haskell
spec :: Spec
spec = do $ around myOperationWithArgument $ do
  describe "Something" $ do
    it "does something" $ \argument -> do
      myFunc argument
```

## Pending
`pending` and `pendingWith` can be used to mark an incomplete spec:

```haskell
main :: IO ()
main = hspec $ do
  describe "Something" $ do
    it "does something" $ do
      pending
    it "does idk" $ do
      pendingWith "This is an incomplete message"
```

## Expectations
```haskell
-- Equality
x `shouldBe` 23

-- Predicates holds
xs `shouldSatisfy` (not . null)

-- Exceptions
xs `shouldTrhow` anyException
```

## Property
Hspec can easily be integrated with QuickCheck in order to test some properties:

```haskell
describe "read" $ do
  it "is inverst to show" $ property $
    \x -> (read . show) x `shouldBe` (x :: Int)
```

This can be simplified importing `Test.Hspec.QuickCheck`:

```haskell
describe "read" $ do
  prop "is inverst to show" $
    \x -> (read . show) x `shouldBe` (x :: Int)
```

## Automatic spec discovery
There is the possibility to automatically preprocess all files inside test folder. This can be made using a specific GHC pragma inside `test/Spec.hs` file:

```haskell
{-# OPTIONS_GHC -F -pgmF hspec-discover #-}
```

After that the src and test folder must share the same structure:
```bash
src/
├── Foo.hs
├── Foo/
│   └── Bar.hs
└── Baz.hs
test/
├── FooSpec.hs
├── Foo/
│   └── BarSpec.hs
└── BazSpec.hs
```
