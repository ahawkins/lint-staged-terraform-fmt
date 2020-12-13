# lint-staged-terraform-fmt

Integrate `lint-staged` and `terraform fmt`.

## Quick Start

**First**: Install

```
$ yarn add -D lint-staged-terraform-fmt
```

**Second**: Add to `lint-staged`:

```
{
  "lint-staged": {
    "*.{tf,tfvars}": "lint-staged-terraform-fmt"
  }
}
```

## Why this project?

`terraform fmt` does not work on a list of files which `lint-staged`
provides. `terraform fmt` works on a directory or stdin.

This project shims the interface between `lint-staged` and `terraform fmt` by looping over the arg list and using `terraform fmt -` to
rewrite individual files.
