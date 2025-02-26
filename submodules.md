# Submodules

Submodules? Now you have more repositories!

## You want to clone a repository with submodules included from the get-go?

```
git clone --recurse-submodules <repo>
```

## You want to clone a repository with submodules included and updated to their latest version from the get-go? (Not recommended)

```
git clone --recurse-submodules --remote-submodules <repo>
```

## You've cloned a repository but the the submodules didn't come with?

```
git submodule update --init --recursive
```

## You need to pull the submodules?

```
git pull --recurse-submodules
```
