# Detached head state

When a user ends up in a "detached head" state, this is a scary situation, but as we know, Git is not scary.

## Setup:

1. Run `source setup.sh` (or `.\setup.ps1` in PowerShell)

## The task

1. Run `git status` and `git log --oneline --graph --all` to see what is going on. <br />
Answer:  <br />
```
HEAD detached at c6bc3dd
nothing to commit, working tree clean
```
```
* a8c914b (master) D
* 5b76325 C
* ddfe696 B
* c6bc3dd (HEAD) A
```

2. Restore normalcy in this repository by moving to `master`
Answer:  <br />
```
git checkout master
```

Note that this task might seem more confusing if you did not run `setup.sh` in your terminal.

We want to have a branch called `the-beginning` that is made from the first commit with message `A`. <br />

3. Can you do this by first causing a detached head? <br />
Answer:  <br />
```
git checkout c6bc3dd
```
```
$ git log --oneline --graph --all

* a8c914b (master) D
* 5b76325 C
* ddfe696 B
* c6bc3dd (HEAD) A
```
```
$ git status

HEAD detached at c6bc3dd
nothing to commit, working tree clean
```

## Useful commands

- `git status`
- `git log --oneline --graph --all`
- `git checkout <ref>` or `git switch --detach <ref>`
