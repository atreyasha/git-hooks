# Pre-commit hooks

This repository contains useful `pre-commit` hooks for various purposes. Here is a description of what they do.

1. `pre-commit-version.sample` is a pre-commit hook which automatically updates the version number of a github badge. This circumvents the need to push your repo to another site. This has been tested with the `shields.io` release-number badge.

2. `pre-commit-readme2tex.sample` is a pre-commit hook which acts as a temporary bug fix to `readme2tex` due to rawgit going down. This essentially reformats svg links in the `README.md` file to contain local svg links and it also helps to remove unused svgs. This has also been discussed in the following issue: https://github.com/leegao/readme2tex/issues/22

## Utility

To use these pre-commit hooks, firstly clone this repository and navigate to its main directory:

```shell
$ git clone https://github.com/AtreyaSh/preCommitHooks && cd preCommitHooks
```

Next, copy the relevant `.sample` executable file into the `.git/hooks/` directory of a desired git repository with its name as `pre-commit`:

```shell
$ cp pre-commit-chosen-name.sample /path/to/repo/.git/hooks/pre-commit
```
