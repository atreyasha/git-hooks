# Pre-commit hooks

This repository contains useful `pre-commit` hooks for various purposes. Here is a description of what they do.

1. `pre-commit-version.sample` is a pre-commit hook which automatically updates the version number of a github badge. This circumvents the need to push your repo to another site. This has been tested with the `shields.io` release-number badge.

2. `pre-commit-readme2tex.sample` is a pre-commit hook which acts as a temporary bug fix to `readme2tex` due to rawgit going down. This essentially reformats svg links in the `README.md` file to contain local svg links and it also helps to remove unused svgs.

# Utility

To use these pre-commit hooks, firstly clone this repository:

```shell
$ git clone https://github.com/AtreyaSh/preCommitHook && cd preCommitHook
```

Next, copy the relevant `.sample` executable file into the `.git/hooks/`directory of a desired git repository:

```shell
$ cp pre-commit-chosen-name.sample /path/to/repo/.git/hooks/
```

Rename the executable file to `pre-commit`

```shell
mv .git/hooks/pre-commit-chosen-name.sample .git/hooks/pre-commit
```
