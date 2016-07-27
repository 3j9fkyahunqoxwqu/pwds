# pwds

**P**rint the path of the current **w**orking **d**irectory, **s**hortly.

The current working directory in your prompt can get uncomfortably large,
leaving little space to type your own commands. With pwds paths like
`~/Code/rust/src/doc/nomicon` are displayed as `~/C/r/s/d/nomicon`.

# Installation

Install pwds with cargo:
``` shell
cargo install pwds
```

Then you need to customize your PS1 in your shell's initialization file, e.g.
`.bashrc`. Here is a standard prompt, the `\w` is an escape code for the current
working directory:
``` shell
PS1='\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '
```
replace `\w` with `$(pwds)`:
``` shell
PS1='\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]$(pwds)\[\033[00m\]\$ '
```
and enjoy a smaller prompt!

# Customization

By default, paths with more than 16 characters are shortened by replacing
directory names with their first character. This can be configured by setting
the `PWDS_LENGTH` environment variable:
``` shell
export PWDS_LENGTH=10
```
The current (most right) directory is never shortened.
