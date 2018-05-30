# envrc -- auto source .envrc of your workspace

## Motivation

[direnv](https://github.com/direnv/direnv) doesn't quite support alias by now.

According to direnv documentation, 

> direnv is actually creating a new bash process to load the stdlib, direnvrc
> and .envrc, and only exports the environment diff back to the original shell

On the contrast, envrc is simpler. It starts a new interactive bash shell and
load the `.envrc` for you. The shell exits and returns your terminal back to
the parent shell after you `cd` out of the directory.

## Why not python?

The first working commit is written in python. But there's noticable time lag
with the python version on my PC. Rewriting it with perl doesn't help either.
Then I decided to switch to rust.

```
$ time envrc.py bash-prompt-command >/dev/null
real    0m0.079s
user    0m0.044s
sys     0m0.004s
```
