# Git Kata: Basic Staging

This kata will examine the staging area of git.

In git we are working with three different areas:

* The working directory where you are making your changes
* The staging area where all changes you have added through `git add` will stay
* The repository where every commit ends up, making your history. To put your staged changes in here you issue the `git commit` command.

A file can have changes both in the working directory and staging area at the same time.
These changes do not have to be the same.

We will also work with `git restore` to restore the staged changes of a file, and `git checkout` to return a file to a previous state.

## Setup

1. Run `source setup.sh` (or `.\setup.ps1` in PowerShell)

## The task

You live in your own repository. There is a file called `file.txt`.

1. What's the content of `file.txt`? <br />
Answer: <br />
`1`

2. Overwrite the content in `file.txt`: `echo 2 > file.txt` to change the state of your file in the working directory (or `sc file.txt '2'` in PowerShell) <br />
Answer: <br />
✅.

3. What does `git diff` tell you? <br />
Answer: <br />
```
--- a/file.txt
+++ b/file.txt
@@ -1 +1 @@
-1
+2
```

4. What does `git diff --staged` tell you? why is this blank? <br />
Answer: <br />
no output, because the changes are still `unstaged`.

5. Run `git add file.txt` to stage your changes from the working directory. <br />
Answer: <br />
✅.

6. What does `git diff` tell you? <br />
Answer: <br />
no output.

7. What does `git diff --staged` tell you? <br />
Answer: <br />
```
--- a/file.txt
+++ b/file.txt
@@ -1 +1 @@
-1
+2
```

8. Overwrite the content in `file.txt`: `echo 3 > file.txt` to change the state of your file in the working directory (or `sc file.txt '3'` in PowerShell). <br />
Answer: <br />
✅.

9. What does `git diff` tell you? <br />
Answer: <br />
```
--- a/file.txt
+++ b/file.txt
@@ -1 +1 @@
-2
+3
```

10. What does `git diff --staged` tell you? <br />
Answer: <br />
```
--- a/file.txt
+++ b/file.txt
@@ -1 +1 @@
-1
+2
```

11. Explain what is happening <br />
Answer: <br />
`git diff` answers the question: "What have you changed but not yet staged?",
`git diff --staged` answers the question: "What have you staged that you are about to commit?".

12. Run `git status` and observe that `file.txt` are present twice in the output. <br />
Answer: <br />
✅.

13. Run `git restore --staged file.txt` to unstage the change <br />
Answer: <br />
✅.

14. What does `git status` tell you now? <br />
Answer: <br />
```
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   file.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

15. Stage the change and make a commit <br />
Answer: <br />
`git add file.txt`, `git commit -m "Modify number"`

16. What does the log look like? <br />
Answer: <br />
```
commit 97581ebb3c613dffa1f49fed41b1db311da215ac (HEAD -> master)
Author: Mohammad Abohasan <mo7ammad.saed@gmail.com>
Date:   Fri Oct 20 16:15:19 2023 +0300

    Modify number

commit 2eee2a569c75301ec8bdab5c46e576bce75c4231
Author: git-katas trainer bot <git-katas@example.com>
Date:   Fri Oct 20 15:53:01 2023 +0300

    1
```

17. Overwrite the content in `file.txt`: `echo 4 > file.txt` (or `sc file.txt '4'` in PowerShell) <br />
Answer: <br />
✅.

18. What is the content of `file.txt`? <br />
Answer: <br />
`4`

19. What does `git status` tell us? <br />
Answer: <br />
```
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   file.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

20. Run `git restore file.txt` <br />
Answer: <br />
✅.

21. What is the content of `file.txt`? <br />
Answer: <br />
`3`

22. What does `git status` tell us? <br />
Answer: <br />
```
On branch master
nothing to commit, working tree clean
```

## Useful commands

- `git add`
- `git commit`
- `git commit -m "My lazy short commit message"`
- `git log`
- `git log -n 5`
- `git log --oneline`
- `git log --oneline --graph`
- `git restore --staged`

## Aliases

You can set up aliases as such:
`git config --global alias.lol 'log --oneline --graph --all'`
This might be useful to you.
