# git-hooks :anchor:

This repository documents git hooks which assist with `python`, `shell`, `R` and `org-mode` development workflows as well as secondary branch rebasing.

## Overview :book:

<details><summary>Pre-commit hook</summary><p>

`pre-commit` contains a useful hook which is, from its name, a workflow that is executed before every commit. The various functions and dependencies in the shell script are described below:

| Function                   | Description                                                                                                          | Dependencies                                      |
|:---------------------------|:---------------------------------------------------------------------------------------------------------------------|:--------------------------------------------------|
| update_python_dependencies | Updates `requirements.txt` to maintain log of python dependencies                                                    | [poetry](https://github.com/python-poetry/poetry) |
| lint_shell_scripts         | Lints all shell scripts with consistent indents                                                                      | [shfmt](https://github.com/mvdan/sh)              |
| lint_R_scripts             | Lints all R scripts for clean code                                                                                   | [styler](https://github.com/r-lib/styler)         |
| convert_org_to_md          | Converts specified `org` file(s) to github-flavored `markdown`, adds a `TOC` and cleans up `TODO` and `DONE` markers | [pandoc](https://github.com/jgm/pandoc)           |

In addition, we provide a `main` function where the user can decide which of the above functions to use.

</p></details>
<details><summary>Post-commit hook</summary><p>

`post-commit` contains a simpler hook which keeps specified secondary branches rebased with a primary branch. Here, we provide only one function:

| Function      | Description                                                                                                                                          | Dependencies |
|:--------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------|:-------------|
| rebase_branch | Rebases a secondary branch with a primary branch. This could be useful to keep one branch up-to-date with another while still offering new features. | -            |

The names of the aforementioned branches can be specified in the `main` function.

</p></details>

## Usage :snowflake:

1. Edit the `main` function(s) of the hooks to customize callable functions and input parameters.

2. In order to initialize both hooks, copy the edited hooks to `./.git/hooks/` in your desired `git` repository. For example:

    ```shell
    $ cp /path/to/pre-commit ./.git/hooks/
    $ cp /path/to/post-commit ./.git/hooks/
    ```

**Note:** These hooks are generally non-invasive, ie. they exit gracefully if dependencies or staged changes are missing and do not interfere with the overall commit process in case of failures.

## Bugs/Issues :bug:

In case of bugs or suggestions for improvements, feel free to open a GitHub issue.
