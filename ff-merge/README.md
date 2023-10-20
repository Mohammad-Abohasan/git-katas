# Git Kata: Fast-forward Merge

## Setup

1. Run `source setup.sh` (or `.\setup.ps1` in PowerShell)

## The task

You again live in your own branch, this time we will be doing a bit of juggling with branches, to show how lightweight branches are in git.

1. Create a (feature)branch called `feature/uppercase` (yes, `feature/uppercase` is a perfectly legal branch name, and a common convention). <br />
Answer:  <br />
✅.

2. Switch to this branch <br />
Answer: <br />
`Switched to a new branch 'feature/uppercase'`

3. What is the output of `git status`? <br />
Answer:  <br />
```
On branch feature/uppercase
nothing to commit, working tree clean
```

4. Edit the greeting.txt to contain an uppercase greeting <br />
Answer:  <br />
✅.

5. Add `greeting.txt` files to staging area and commit <br />
Answer:  <br />
```
[feature/uppercase fef7055] Convert greeting to uppercase
 1 file changed, 1 insertion(+), 1 deletion(-)
```

6. What is the output of `git branch`? <br />
Answer:  <br />
```
* feature/uppercase
  master
```

7. What is the output of `git log --oneline --graph --all`

   *Remember: You want to update the master branch so it also has all the changes currently on the feature branch. The command 'git merge [branch name]' takes one branch as argument from which it takes changes. The branch pointed to by HEAD (currently checked out branch) is then updated to also include these changes.* <br />

Answer:  <br />
```
* fef7055 (HEAD -> feature/uppercase) Convert greeting to uppercase
* 5f54f91 (master) Add content to greeting.txt
* 94c861c Add file greeting.txt
```

8. Switch to the `master` branch <br />
Answer:  <br />
`Switched to branch 'master'`

9. Use `cat` to see the contents of the greetings <br />
Answer:  <br />
`hello`

10. Diff the branches <br />
Answer:  <br />
```
--- a/greeting.txt
+++ b/greeting.txt
@@ -1 +1 @@
-hello
+HELLO
```

11. Merge the branches <br />
Answer:  <br />
```
Updating 5f54f91..fef7055
Fast-forward
 greeting.txt | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
```

12. Use `cat` to see the contents of the greetings <br />
Answer:  <br />
`HELLO`

13. Delete the uppercase branch <br />
Answer: <br />
```
Deleted branch feature/uppercase (was fef7055).
```


## Useful commands

- `git branch`
- `git branch <branch-name>`
- `git branch -d <branch-name>`
- `git switch`
- `git branch -v`
- `git add`
- `git commit`
- `git commit -m`
- `git merge <branch>`
- `git diff <branchA> <branchB>`
- `git log --oneline --graph --all`
