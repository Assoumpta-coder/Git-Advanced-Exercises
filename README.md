# Git-Advanced-Exercises
## Challenges

### Getting Started

```bash
Microsoft Windows [Version 10.0.22621.4317]
(c) Microsoft Corporation. All rights reserved.

C:\Users\airah>git clone https://github.com/Assoumpta-coder/Git-Advanced-Exercises.git
Cloning into 'Git-Advanced-Exercises'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Receiving objects: 100% (3/3), done.

C:\Users\airah>cd Git-Advanced-Exercises

C:\Users\airah\Git-Advanced-Exercises> code .

C:\Users\airah\Git-Advanced-Exercises>
```
### Part 1 Refining Git History

#### Missing File Fix:

```bash
airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ touch test{1..4}.md
git add test1.md && git commit -m "chore: Create initial file"
git add test2.md && git commit -m "chore: Create another file"
git add test3.md && git commit -m "chore: Create third and fourth files"
[main dc95d0f] chore: Create initial file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
[main 5aa737a] chore: Create another file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
[main 6c7b186] chore: Create third and fourth files
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test4.md

no changes added to commit (use "git add" and/or "git commit -a")

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git log --oneline
6c7b186 (HEAD -> main) chore: Create third and fourth files
5aa737a chore: Create another file
dc95d0f chore: Create initial file
898a885 (origin/main, origin/HEAD) Initial commit

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git add test4.md

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git commit --amend -m "chore: Create third, fourth files"
[main f53c0d5] chore: Create third, fourth files
 Date: Wed Jul 30 14:42:33 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
```
#### Editing Commit History

```bash
$ git log --oneline
f53c0d5 (HEAD -> main) chore: Create third, fourth files
5aa737a chore: Create another file
dc95d0f chore: Create initial file
898a885 (origin/main, origin/HEAD) Initial commit

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git log --oneline
f53c0d5 (HEAD -> main) chore: Create third, fourth files
5aa737a chore: Create another file
dc95d0f chore: Create initial file
898a885 (origin/main, origin/HEAD) Initial commit

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git rebase -i HEAD~2
error: cannot rebase: You have unstaged changes.
error: Please commit or stash them.

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git add .
# r, reword <commit> = use commit, but edit the commit message
# e, edit <commit> = use commit, but stop for amending
# s, squash <commit> = use commit, but meld into previous commit
# f, fixup [-C | -c] <commit> = like "squash" but keep only the previous
#                    commit's log message, unless -C is used, in which case
.git/rebase-merge/git-rebase-todo [unix] (15:12 30/07/2025)                                                                       10,1 25%
# p, pick <commit> = use commit
# r, reword <commit> = use commit, but edit the commit message
# e, edit <commit> = use commit, but stop for amending
# s, squash <commit> = use commit, but meld into previous commit
# f, fixup [-C | -c] <commit> = like "squash" but keep only the previous
#                    commit's log message, unless -C is used, in which case
#                    keep only this commit's message; -c is same as -C but
.git/rebase-merge/git-rebase-todo [unix] (15:12 30/07/2025)                                                                       10,1 23%
# p, pick <commit> = use commit
# r, reword <commit> = use commit, but edit the commit message
# e, edit <commit> = use commit, but stop for amending
# s, squash <commit> = use commit, but meld into previous commit
# f, fixup [-C | -c] <commit> = like "squash" but keep only the previous
#                    commit's log message, unless -C is used, in which case
#                    keep only this commit's message; -c is same as -C but
#                    opens the editor
.git/rebase-merge/git-rebase-todo [unix] (15:12 30/07/2025)                                                                       10,1 24%
# Commands:
# p, pick <commit> = use commit
# r, reword <commit> = use commit, but edit the commit message
# e, edit <commit> = use commit, but stop for amending
# s, squash <commit> = use commit, but meld into previous commit
# f, fixup [-C | -c] <commit> = like "squash" but keep only the previous
#                    commit's log message, unless -C is used, in which case
#                    keep only this commit's message; -c is same as -C but
#                    opens the editor
.git/rebase-merge/git-rebase-todo [unix] (15:12 30/07/2025)                                                                       10,1 20%
# Commands:
# p, pick <commit> = use commit
# r, reword <commit> = use commit, but edit the commit message
# e, edit <commit> = use commit, but stop for amending
# s, squash <commit> = use commit, but meld into previous commit
# f, fixup [-C | -c] <commit> = like "squash" but keep only the previous
#                    commit's log message, unless -C is used, in which case
#                    keep only this commit's message; -c is same as -C but
#                    opens the editor
# x, exec <command> = run command (the rest of the line) using shell
.git/rebase-merge/git-rebase-todo [unix] (15:12 30/07/2025)                                                                       10,1 21%
#
#         message (or the oneline, if no original merge commit was
git commit -m "wip: saving changes before rebase"
[main e8cb2ed] wip: saving changes before rebase
 1 file changed, 86 insertions(+), 1 deletion(-)

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git rebase -i HEAD~2
Successfully rebased and updated refs/heads/main.

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git rebase -i HEAD~2
Successfully rebased and updated refs/heads/main.

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ 
```