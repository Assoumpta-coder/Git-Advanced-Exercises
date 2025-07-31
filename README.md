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
$ git  add .

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git commit -m "Done with Editing Commit History Exercise"
[main bdda474] Done with Editing Commit History Exercise
 1 file changed, 76 insertions(+), 1 deletion(-)

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git push -u origin main
Enumerating objects: 15, done.
Counting objects: 100% (15/15), done.
Delta compression using up to 4 threads
Compressing objects: 100% (12/12), done.
Writing objects: 100% (13/13), 2.63 KiB | 244.00 KiB/s, done.
Total 13 (delta 5), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (5/5), done.
To https://github.com/Assoumpta-coder/Git-Advanced-Exercises.git
   898a885..bdda474  main -> main
branch 'main' set up to track 'origin/main'.

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$
```

#### Keeping History Tidy - Squashing Commits:

```bash
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

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
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
$ git  add .

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git commit -m "Done with Editing Commit History Exercise"
[main bdda474] Done with Editing Commit History Exercise
 1 file changed, 76 insertions(+), 1 deletion(-)

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git push -u origin main
Enumerating objects: 15, done.
Counting objects: 100% (15/15), done.
Delta compression using up to 4 threads
Compressing objects: 100% (12/12), done.
Writing objects: 100% (13/13), 2.63 KiB | 244.00 KiB/s, done.
Total 13 (delta 5), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (5/5), done.
To https://github.com/Assoumpta-coder/Git-Advanced-Exercises.git
   898a885..bdda474  main -> main
branch 'main' set up to track 'origin/main'.

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$
 *  History restored 


airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git log --oneline
bdda474 (HEAD -> main, origin/main, origin/HEAD) Done with Editing Commit History Exercise
e8cb2ed wip: saving changes before rebase
f53c0d5 chore: Create third, fourth files
5aa737a chore: Create another file
dc95d0f chore: Create initial file
898a885 Initial commit

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git rebase -i HEAD~4
error: cannot rebase: You have unstaged changes.
error: Please commit or stash them.

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git add .

pick 5aa737a chore: Create another file
airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git rebase -i HEAD~4
error: cannot rebase: Your index contains uncommitted changes.
error: Please commit or stash them.

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git add .
git commit -m "wip: saving changes before rebase"
[main fada190] wip: saving changes before rebase
 1 file changed, 29 insertions(+), 1 deletion(-)

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git rebase -i HEAD~5
Successfully rebased and updated refs/heads/main.

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
pick f53c0d5 chore: Create third, fourth files

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git log --oneline
fada190 (HEAD -> main) wip: saving changes before rebase
pick f53c0d5 chore: Create third, fourth files
bdda474 (origin/main, origin/HEAD) Done with Editing Commit History Exercise
e8cb2ed wip: saving changes before rebase
f53c0d5 chore: Create third, fourth files
5aa737a chore: Create another file
dc95d0f chore: Create initial file
898a885 Initial commit

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git rebase -i HEAD~4
Successfully rebased and updated refs/heads/main.

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git rebase -i HEAD~4
Successfully rebased and updated refs/heads/main.
pick 5aa737a chore: Create another file

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git log --oneline
fada190 (HEAD -> main) wip: saving changes before rebase
pick dc95d0f chore: Create initial file
bdda474 (origin/main, origin/HEAD) Done with Editing Commit History Exercise
e8cb2ed wip: saving changes before rebase
f53c0d5 chore: Create third, fourth files
5aa737a chore: Create another file
dc95d0f chore: Create initial file
898a885 Initial commit

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git rebase -i HEAD~5
Successfully rebased and updated refs/heads/main.

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git rebase -i HEAD~6
Successfully rebased and updated refs/heads/main.
#         specified); use -c <commit> to reword the commit message

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git log --oneline
fada190 (HEAD -> main) wip: saving changes before rebase
bdda474 (origin/main, origin/HEAD) Done with Editing Commit History Exercise
e8cb2ed wip: saving changes before rebase
f53c0d5 chore: Create third, fourth files
5aa737a chore: Create another file
dc95d0f chore: Create initial file
898a885 Initial commit

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git rebase -i HEAD~6
error: Your local changes to the following files would be overwritten by checkout:
        README.md
Please commit your changes or stash them before you switch branches.
Aborting
error: could not detach HEAD
#         message (or the oneline, if no original merge commit was

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git log --oneline
fada190 (HEAD -> main) wip: saving changes before rebase
pick 5aa737a chore: Create another file
bdda474 (origin/main, origin/HEAD) Done with Editing Commit History Exercise
e8cb2ed wip: saving changes before rebase
f53c0d5 chore: Create third, fourth files
5aa737a chore: Create another file
dc95d0f chore: Create initial file
898a885 Initial commit

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git rebase -i HEAD~2
Successfully rebased and updated refs/heads/main.

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git rebase -i HEAD~5
Successfully rebased and updated refs/heads/main.

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git add README.md
git commit -m "chore: update README before rebase"
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ $ git add README.md
bash: $: command not found

pick dc95d0f chore: Create initial file
airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
pick dc95d0f chore: Create initial file
$ git add README.md
pick dc95d0f chore: Create initial file

#         message (or the oneline, if no original merge commit was
airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git commit -m "chore: update README before rebase"
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git rebase -i HEAD~6
hint: Waiting for your editor to close the file...       1 [sig] bash 2189! sigpacket::process: Suppressing signal 18 to win32 process (pid 10924)
1141213 [sig] bash 2189! sigpacket::process: Suppressing signal 18 to win32 process (pid 10924)
1751934 [sig] bash 2189! sigpacket::process: Suppressing signal 18 to win32 process (pid 10924)
# u, update-ref <ref> = track a placeholder for the <ref> to be updated
error: missing arguments for pick
error: invalid line 3: pick
error: invalid command '3c0d5'
error: invalid line 4: 3c0d5 chore: Create third, fourth files
You can fix this with 'git rebase --edit-todo' and then run 'git rebase --continue'.
Or you can abort the rebase with 'git rebase --abort'.

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main|REBASE)
$ git rebase --edit-todo
error: missing arguments for pick
error: invalid line 3: pick
error: invalid command '3c0d5'
#         message (or the oneline, if no original merge commit was
#    pick e8cb2ed wip: saving changes before rebase
error: invalid line 4: 3c0d5 chore: Create third, fourth files
error: missing arguments for pick
error: invalid line 3: pick
error: invalid command '3c0d5'
error: invalid line 4: 3c0d5 chore: Create third, fourth files
You can fix this with 'git rebase --edit-todo' and then run 'git rebase --continue'.
Or you can abort the rebase with 'git rebase --abort'.

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main|REBASE)
$ git rebase --abort

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git rebase -i HEAD~6
[detached HEAD 3fdad8e] chore: Create initial file
 Date: Wed Jul 30 14:42:31 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/main.

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git log --oneline
603f83b (HEAD -> main) wip: saving changes before rebase
7cec419 Done with Editing Commit History Exercise
965aa1c wip: saving changes before rebase
269cc78 chore: Create third, fourth files
3fdad8e chore: Create initial file
898a885 Initial commit

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git log -1
commit 603f83bfc1cb352652cc19889fc44849d3d37792 (HEAD -> main)
Author: Assoumpta Uwabera <assoumpta.uwabera22a@kepler.org>
Date:   Thu Jul 31 11:41:03 2025 +0200

    wip: saving changes before rebase

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git log
commit 603f83bfc1cb352652cc19889fc44849d3d37792 (HEAD -> main)
Author: Assoumpta Uwabera <assoumpta.uwabera22a@kepler.org>
Date:   Thu Jul 31 11:41:03 2025 +0200

    wip: saving changes before rebase

commit 7cec419ac0365f0a3becedd128a20a4ca3be65b8
Author: Assoumpta Uwabera <assoumpta.uwabera22a@kepler.org>
Date:   Wed Jul 30 17:49:07 2025 +0200

    Done with Editing Commit History Exercise

commit 965aa1c555e653a723e1f9843c300b38626dcc5d
Finishing logfile... (interrupt to abort)
airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git show 3fdad8e
commit 3fdad8e9ce7193a10519938d21eb3eab358f5ab8
Author: Assoumpta Uwabera <assoumpta.uwabera22a@kepler.org>
Date:   Wed Jul 30 14:42:31 2025 +0200

    chore: Create initial file

    chore: Create another file

    chore: Create initial file and another file

    ...

diff --git a/test1.md b/test1.md
$ git push origin main --force-with-lease
Enumerating objects: 16, done.
Counting objects: 100% (16/16), done.
Delta compression using up to 4 threads
Compressing objects: 100% (13/13), done.
Writing objects: 100% (14/14), 2.96 KiB | 168.00 KiB/s, done.
Total 14 (delta 6), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (6/6), done.
To https://github.com/Assoumpta-coder/Git-Advanced-Exercises.git
 + bdda474...603f83b main -> main (forced update)

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git add .
warning: in the working copy of 'how 3fdad8e', LF will be replaced by CRLF the next time Git touches it

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$ git push origin main --force-with-lease
Everything up-to-date

airah@Assoumpta MINGW64 ~/Git-Advanced-Exercises (main)
$

```

####
