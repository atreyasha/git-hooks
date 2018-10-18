# Pre-commit hook for updating version number

This is a pre-commit git hook optimized for R-packages built with lucode. Upon every commit, it checks the version number of a GitHub version badge in `README.md` against the version listed in the `DESCRIPTION` file. If there are differences, the version on `README.md` is updated using that in `DESCRIPTION`.

To use this pre-commit hook, firstly clone this repository:

```shell
git clone https://github.com/AtreyaSh/preCommitBadgeUpdate && cd preCommitBadgeUpdate
```

Next, simply copy the `pre-commit` executable file into the `/.git/hooks/`directory of a desired git repository:

```shell
cp pre-commit /path/to/repo/.git/hooks/
```
