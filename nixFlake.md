---
date: 2020-12-09T19:17
tags:
  - linux/nixos
  - flake
---

# Flake
**Flake** is nix feature that aim to resolve problem raised from nix channels and nix fetchers. Is like poetry or npm that pin specific versions/commits of dependencies

It has a user friendly git repo pointer
```
github:repoOwner/repo#commandInNixFile
```
and also supports registries to avoid writing all github path every time:
```
github:NixOS/nixpkgs#cowsay
```
become
```
nixpkgs#cowsay
```
if a registry like this is added before:
```
nix regitry add nixpkgs github:NixOS/nixpkgs/<version>
```

## Flake file structure
The flake file structure is:

* ***description*** → one-line description shown by `nix flake info`;
* ***inputs*** → other flake files passed as arguments to outputs;
* ***outputs*** → function that produces an attribute set. `self` is used to denotes *this* flake;
* ***return set*** → set returned by outputs has arbitrary values expect for some that are standard;
* ***metadata*** → there are some metadata (like nix derivations).

### Outputs
Also outputs has an own internal structure:

* `<system>` → identify the platform es. *"x86_64-linux"*
* `<attr>` → attribute name
* `<flake>` → flake name like *"nixpkgs"*
* `<store-path>` → /nix/store path

All these tag must be used inside the file nix like explained in the [documentation](https://nixos.wiki/wiki/Flakes)
