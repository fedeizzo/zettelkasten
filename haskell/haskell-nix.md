---
date: 2021-03-13T17:22
tags:
  - haskell/nix
  - haskell/cabal
  - haskell/howto
  - linux/nixos
---

# Nix
Here are listed some useful tips for create and manage an haskell project on a nix environment.

## Cabal
List of command to create a new project with [[cabal]]:

1. `nix-shell --pure -p ghc cabal-install --run "cabal init --interactive"`
2. `nix-shell --pure -p cabal2nix --run "cabal2nix ." > default.nix`

After that a *release.nix* file is needed:

```nix
let
  pkgs = import <nixpkgs> { };
in
  pkgs.haskellPackages.callPackage ./default.nix {  }
```

now, with nix-build, there is the possibility to compile the project.

There is also the possibility to define default.nix as follow:

```nix
(import <nixpkgs> { }).haskellPackages.callCabal2nix "my-taffybar" ./. { }
```

In this way user do not need to call command on point 2 every time they modify cabal file.

### Dev shell and lorri
To run dev shell: `nix-shell --attr env release.nix`

If lorri and direnv is enable:

1. `lorri init`
2. direnv allow

replace *shell.nix* file content with:

```nix
{ nixpkgs ? import <nixpkgs> {} }:
let
  inherit (nixpkgs) pkgs;
  inherit (pkgs) haskellPackages;

  project = import ./release.nix;
in
pkgs.stdenv.mkDerivation {
  name = "shell";
  buildInputs = project.env.nativeBuildInputs ++ [
    haskellPackages.cabal-install
    haskellPackages.brittany
  ];
}
```
[Source](https://maybevoid.com/posts/2019-01-27-getting-started-haskell-nix.html)
