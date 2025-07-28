# Git-Exercises
## Getting Started
```bash 
hp@Dorine MINGW64 ~
$ git clone https://github.com/Joie-Dorine-Habarugira-dodo/Git-Exercises.git
fatal: destination path 'Git-Exercises' already exists and is not an empty directory.

hp@Dorine MINGW64 ~
$ git clone https://github.com/Joie-Dorine-Habarugira-dodo/Git-Exercises.git
fatal: destination path 'Git-Exercises' already exists and is not an empty directory.       

$ git clone https://github.com/Joie-Dorine-Hab$ git clone https://github.com/Joie-Dorine-Habarugira-dodo/Git-Exercises-2.git
Cloning into 'Git-Exercises-2'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.   
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Receiving objects: 100% (3/3), done.

hp@Dorine MINGW64 ~
$ cd Git-Exercises-2

hp@Dorine MINGW64 ~/Git-Exercises-2 (main)    
$ touch test{1..4}.md
git add test1.md && git commit -m "chore: Create initial file"
git add test2.md && git commit -m "chore: Create another file"
git add test3.md && git commit -m "chore: Create third and fourth files"
[main 5711959] chore: Create initial file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
[main b6da791] chore: Create third and fourth files
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 ```

## Part 1: Refining Git History

### 1. Missing File Fix
```bash
hp@Dorine MINGW64 ~/Git-Exercises-2 (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

hp@Dorine MINGW64 ~/Git-Exercises-2 (main)
$ git log
commit b6da791a75fb81a19e8ec9556e20ce45549b44fb (HEAD -> main)
Author: Joie-Dorine-Habarugira-dodo <joiedorine.habarugira22a@kepler.org>
Date:   Mon Jul 28 10:35:07 2025 +0200

    chore: Create third and fourth files

commit 382c05e3b3e3af70be6b9c97d884805e3d6f5453
Author: Joie-Dorine-Habarugira-dodo <joiedorine.habarugira22a@kepler.org>

hp@Dorine MINGW64 ~/Git-Exercises-2 (main)
$ git add test1.md && git commit -m "chore: Create initial file"
On branch main
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

hp@Dorine MINGW64 ~/Git-Exercises-2 (main)    
$ git add test4.md
nd fourth files"
[main 4005786] chore: Create third and fourth nd fourth files"
[main 4005786] chore: Create third and fourth files
 Date: Mon Jul 28 10:35:07 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md

hp@Dorine MINGW64 ~/Git-Exercises-2 (main)    
[detached HEAD 83dc984] chore: Create second file
 Date: Mon Jul 28 10:35:06 2025 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/main.
```

### 2. Editing Commit History
```bash
hp@Dorine MINGW64 ~/Git-Exercises-2 (main)
$ git rebase -i HEAD~2
Successfully rebased and updated refs/heads/main.
hp@Dorine MINGW64 ~/Git-Exercises-2 (main)
$ git log
commit 6a241cde8df3669fac8469ffe218c632d613f641 (HEAD -> main)
Author: Joie-Dorine-Habarugira-dodo <joiedorine.habarugira22a@kepler.org>
Date:   Mon Jul 28 10:35:07 2025 +0200

    chore: Create third and fourth files

commit 83dc984e5701a9e97179c47ecd27829a2b7204db
Author: Joie-Dorine-Habarugira-dodo <joiedorine.habarugira22a@kepler.org>
Date:   Mon Jul 28 10:35:06 2025 +0200

    chore: Create second file

commit 5711959c9e32e901ea4ec91c4bd41a4cd49b2e24
Author: Joie-Dorine-Habarugira-dodo <joiedorine.habarugira22a@kepler.org>
Date:   Mon Jul 28 10:35:06 2025 +0200

    chore: Create initial file

commit ba97a5c02402f76a8474164cee2ff8e2fa18b15d (origin/main, origin/HEAD)
Author: Joie-Dorine-Habarugira-dodo <hjoydoreen08@gmail.com>
Date:   Mon Jul 28 10:26:06 2025 +0200

    Initial commit
```

### 3. Keeping History Tidy - Squashing Commits
```bash
hp@Dorine MINGW64 ~/Git-Exercises-2 (main)
$ git rebase -i HEAD~2
interactive rebase in progress; onto 5711959
Last command done (1 command done):
   pick 5711959 chore: Create initial file
Next commands to do (2 remaining commands):
   squash 83dc984 chore: Create second file
   pick 6a241cd chore: Create third and fourth files
  (use "git rebase --edit-todo" to view and edit)
You are currently rebasing branch 'main' on '5711959'.
  (all conflicts fixed: run "git rebase --continue")

nothing to commit, working tree clean
The previous cherry-pick is now empty, possibly due to conflict resolution.
If you wish to commit it anyway, use:

    git commit --allow-empty

Otherwise, please use 'git rebase --skip'
Could not apply 5711959... chore: Create initial file

hp@Dorine MINGW64 ~/Git-Exercises-2 (main|REBASE 1/3)
$ git rebase -i HEAD~2
fatal: It seems that there is already a rebase-merge directory, and
I wonder if you are in the middle of another rebase.  If that is the 
case, please try
        git rebase (--continue | --abort | --skip)
If that is not the case, please
        rm -fr ".git/rebase-merge"
and run me again.  I am stopping in case you still have something    
valuable there.


hp@Dorine MINGW64 ~/Git-Exercises-2 (main|REBASE 1/3)
$ git rebase --continue
[detached HEAD 0e18bfc] chore: Create initial and second file
 Date: Mon Jul 28 10:35:06 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/main.

hp@Dorine MINGW64 ~/Git-Exercises-2 (main)
$ git log
commit 391ef8b4bd24d2a98c462f6644c315e8b3a38bcd (HEAD -> main)
Author: Joie-Dorine-Habarugira-dodo <joiedorine.habarugira22a@kepler.org>
Date:   Mon Jul 28 10:35:07 2025 +0200

    chore: Create third and fourth files

commit 0e18bfcf889ab670d3ec9d78453a3828427e364d
Author: Joie-Dorine-Habarugira-dodo <joiedorine.habarugira22a@kepler.org>
Date:   Mon Jul 28 10:35:06 2025 +0200

    chore: Create initial and second file

commit ba97a5c02402f76a8474164cee2ff8e2fa18b15d (origin/main, origin/HEAD)
Author: Joie-Dorine-Habarugira-dodo <hjoydoreen08@gmail.com>
Date:   Mon Jul 28 10:26:06 2025 +0200

    Initial commit
```

### 4. Splitting a Commit
```bash
hp@Dorine MINGW64 ~/Git-Exercises-2 (main)
$ git rest HEAD~1
git: 'rest' is not a git command. See 'git --help'.

The most similar commands are
        restore
        reset

hp@Dorine MINGW64 ~/Git-Exercises-2 (main)
$ git reset HEAD~1

hp@Dorine MINGW64 ~/Git-Exercises-2 (main)
$ git log
commit 0e18bfcf889ab670d3ec9d78453a3828427e364d (HEAD -> main)
Author: Joie-Dorine-Habarugira-dodo <joiedorine.habarugira22a@kepler.org>
commit 0e18bfcf889ab670d3ec9d78453a3828427e364d (HEAD -> main)       
Author: Joie-Dorine-Habarugira-dodo <joiedorine.habarugira22a@kepler.org>
Date:   Mon Jul 28 10:35:06 2025 +0200

    chore: Create initial and second file

commit ba97a5c02402f76a8474164cee2ff8e2fa18b15d (origin/main, origin/HEAD)
Author: Joie-Dorine-Habarugira-dodo <hjoydoreen08@gmail.com>
Date:   Mon Jul 28 10:26:06 2025 +0200

    Initial commit

hp@Dorine MINGW64 ~/Git-Exercises-2 (main)
$ git add test3.md

hp@Dorine MINGW64 ~/Git-Exercises-2 (main)
$ git commit -m "chore: Create third file"
[main 4332df4] chore: Create third file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

hp@Dorine MINGW64 ~/Git-Exercises-2 (main)
$ git add test4.md

hp@Dorine MINGW64 ~/Git-Exercises-2 (main)
$ git commit -m "chore: Create fourth file"
[main a5e27a7] chore: Create fourth file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md
```

### 5. Advanced Squashing
```bash
hp@Dorine MINGW64 ~/Git-Exercises-2 (main)
$ git rebase -i HEAD~2
[detached HEAD c2af3d4] chore: Create third and fourth file
 Date: Mon Jul 28 11:11:59 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/main.
```

### 6. Dropping a Commit
```bash
hp@Dorine MINGW64 ~/Git-Exercises-2 (main)    
$ touch unwanted.txt

hp@Dorine MINGW64 ~/Git-Exercises-2 (main)    
$ git add unwanted.txt

hp@Dorine MINGW64 ~/Git-Exercises-2 (main)    
$ git commit -m "Unwanted commit"
[main 7d4e71c] Unwanted commit
 1 file changed, 1 insertion(+)
 create mode 100644 unwanted.txt

hp@Dorine MINGW64 ~/Git-Exercises-2 (main)    
$ git log
commit 7d4e71c6f97c0ed5a7c7657359f629fde5f281fa (HEAD -> main)
Author: Joie-Dorine-Habarugira-dodo <joiedorine.habarugira22a@kepler.org>
Date:   Mon Jul 28 11:21:40 2025 +0200        

    Unwanted commit

commit c2af3d4b0602dbda70567ce671d1d556a1de269b
Author: Joie-Dorine-Habarugira-dodo <joiedorine.habarugira22a@kepler.org>
Date:   Mon Jul 28 11:11:59 2025 +0200        

    chore: Create third and fourth file       

commit 0e18bfcf889ab670d3ec9d78453a3828427e364d
Author: Joie-Dorine-Habarugira-dodo <joiedorine.habarugira22a@kepler.org>

hp@Dorine MINGW64 ~/Git-Exercises-2 (main)    
$ git rebase -i HEAD~1
hint: Waiting for your editor to close the fil
Successfully rebased and updated refs/heads/main.

hp@Dorine MINGW64 ~/Git-Exercises-2 (main)    
$ git log
commit c2af3d4b0602dbda70567ce671d1d556a1de269b (HEAD -> main)
Author: Joie-Dorine-Habarugira-dodo <joiedorine.habarugira22a@kepler.org>
Date:   Mon Jul 28 11:11:59 2025 +0200        

    chore: Create third and fourth file       

commit 0e18bfcf889ab670d3ec9d78453a3828427e364d
```

### 7. Reordering Commits
```bash
hp@Dorine MINGW64 ~/Git-Exercises-2 (main)    
$ git rebase -i HEAD~4
fatal: invalid upstream 'HEAD~4'

$ git rebase -i HEAD~3
fatal: invalid upstream 'HEAD~3'

hp@Dorine MINGW64 ~/Git-Exercises-2 (main)
$ git rebase -i
hint: Waiting for your editor to close the filSuccessfully rebased anhp@Dorine MINGW64 ~/Git-Exercises-2 (main)
```

### 8. Cherry-Picking Commits
```bash
$ git checkout -b ft/branch
Switched to a new branch 'ft/branch'

hp@Dorine MINGW64 ~/Git-Exercises-2 (ft/branch)
$ touch test5.md

hp@Dorine MINGW64 ~/Git-Exercises-2 (ft/branch)
$ echo "This is test 5" > test5.md

hp@Dorine MINGW64 ~/Git-Exercises-2 (ft/branch)
$ git add test5.md
warning: in the working copy of 'test5.md', LF will be replaced by CRLF the next time Git touches it

hp@Dorine MINGW64 ~/Git-Exercises-2 (ft/branch)
$ git commit -m "Implemented test 5"
[ft/branch 3d7b94a] Implemented test 5
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

hp@Dorine MINGW64 ~/Git-Exercises-2 (ft/branch)
$ git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

hp@Dorine MINGW64 ~/Git-Exercises-2 (main)
$ git log ft/branch --oneline
3d7b94a (ft/branch) Implemented test 5
847a8c3 (HEAD -> main) chore: Create initial and second file
830bbcd chore: Create third and fourth file
ba97a5c (origin/main, origin/HEAD) Initial commit

hp@Dorine MINGW64 ~/Git-Exercises-2 (main)
$ git cherry-pick 3d7b94a
[main d49dd66] Implemented test 5
 Date: Mon Jul 28 11:38:23 2025 +0200
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

hp@Dorine MINGW64 ~/Git-Exercises-2 (main)
$ git log --oneline
d49dd66 (HEAD -> main) Implemented test 5
847a8c3 chore: Create initial and second file
830bbcd chore: Create third and fourth file
ba97a5c (origin/main, origin/HEAD) Initial commit
```

### 9. Visualizing Commit History (Bonus)
```bash
hp@Dorine MINGW64 ~/Git-Exercises-2 (main)    
$ git log --oneline -- graph --all

hp@Dorine MINGW64 ~/Git-Exercises-2 (main)    
$ git log --oneline -- graph --all --decorate 

hp@Dorine MINGW64 ~/Git-Exercises-2 (main)    
$ git log -- graph --all --decorate

* d49dd66 (HEAD -> main) Implemented test 5
| * 3d7b94a (ft/branch) Implemented test 5
|/
* 847a8c3 chore: Create initial and second file
* 830bbcd chore: Create third and fourth file
* ba97a5c (origin/main, origin/HEAD) Initial commit
```

### 10. Understanding Reflogs (Bonus)
```bash
hp@Dorine MINGW64 ~/Git-Exercises-2 (main)
$ git reflog
d49dd66 (HEAD -> main) HEAD@{0}: cherry-pick: Implemented test 5
847a8c3 HEAD@{1}: checkout: moving from ft/branch to main
3d7b94a (ft/branch) HEAD@{2}: commit: Implemented test 5
847a8c3 HEAD@{3}: checkout: moving from main to ft/branch
847a8c3 HEAD@{4}: rebase (finish): returning to refs/heads/main      
847a8c3 HEAD@{5}: rebase (pick): chore: Create initial and second file
830bbcd HEAD@{6}: rebase (pick): chore: Create third and fourth file 
ba97a5c (origin/main, origin/HEAD) HEAD@{7}: rebase (start): checkout refs/remotes/origin/main
c2af3d4 HEAD@{8}: rebase (finish): returning to refs/heads/main      
c2af3d4 HEAD@{9}: rebase (start): checkout HEAD~1
7d4e71c HEAD@{10}: commit: Unwanted commit
c2af3d4 HEAD@{11}: rebase (finish): returning to refs/heads/main     
c2af3d4 HEAD@{12}: rebase (squash): chore: Create third and fourth file
4332df4 HEAD@{13}: rebase (start): checkout HEAD~2
a5e27a7 HEAD@{14}: commit: chore: Create fourth file
4332df4 HEAD@{15}: commit: chore: Create third file
0e18bfc HEAD@{16}: reset: moving to HEAD~1
391ef8b HEAD@{17}: rebase (finish): returning to refs/heads/main     
391ef8b HEAD@{18}: rebase (pick): chore: Create third and fourth files
0e18bfc HEAD@{19}: rebase (squash): chore: Create initial and second file
5711959 HEAD@{20}: rebase (start): checkout HEAD~2
6a241cd HEAD@{21}: rebase (finish): returning to refs/heads/main     
6a241cd HEAD@{22}: rebase (start): checkout HEAD~2
6a241cd HEAD@{23}: rebase (finish): returning to refs/heads/main     
6a241cd HEAD@{24}: rebase (pick): chore: Create third and fourth files
83dc984 HEAD@{25}: rebase (reword): chore: Create second file        
382c05e HEAD@{26}: rebase: fast-forward
5711959 HEAD@{27}: rebase (start): checkout HEAD~2
4005786 HEAD@{28}: commit (amend): chore: Create third and fourth files
b6da791 HEAD@{29}: commit: chore: Create third and fourth files      
382c05e HEAD@{30}: commit: chore: Create another file
5711959 HEAD@{31}: commit: chore: Create initial file
ba97a5c (origin/main, origin/HEAD) HEAD@{32}: clone: from https://github.com/Joie-Dorine-Habarugira-dodo/Git-Exercises-2.git
```