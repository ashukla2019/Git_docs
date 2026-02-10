# 🧠 Git Complete Reference Guide (All Levels)

> From beginner → advanced → Git internals  
> One file. One source of truth.

---

## 🔁 Git File Flow (Mental Model)

Working Directory
|
| git add
v
Staging Area (Index)
|
| git commit
v
Local Repository (.git)
|
| git push
v
Remote Repository (GitHub / GitLab)


---

## 1️⃣ Git Setup & Initialization

```bash
git --version
git config --global user.name "Your Name"
git config --global user.email "you@email.com"
git config --list
git init
-----------------------------------------
2️⃣ Working Directory
You edit files here
git status
git diff
git diff file.txt
Ignore Files
.gitignore

node_modules/
.env
*.log
--------------------------------------------------------------
3️⃣ Staging Area (Index)
Working Directory → Staging Area
git add file.txt
git add .
git restore --staged file.txt
📌 Select what goes into the next commit
-----------------------------------------------------------------
4️⃣ Local Repository (Commits)
Staging Area → Local Repo
git commit -m "message"
git commit --amend
git log
git log --oneline --graph --all
---------------------------------------------------------------
5️⃣ Branching
main
 │
 ●────●────●
       \
        ●────● feature
git branch
git branch feature
git checkout feature
git checkout -b feature
git branch -d feature
----------------------------------------------------------------
6️⃣ Merge vs Rebase
Merge
●──●──●
      \
       ●──●
git checkout main
git merge feature
Rebase
●──●──●──●──●
git checkout feature
git rebase main
---------------------------------------
7️⃣ Remote Repository
Local Repo → Remote Repo
git remote add origin URL
git remote -v
git push origin main
git push -u origin main
git pull origin main
git fetch
-------------------------------------
8️⃣ Clone
Remote Repo → Local Repo + Working Dir
git clone URL

------------------------------------------
9️⃣ Stash
Dirty Working Dir → Clean
git stash
git stash list
git stash apply
git stash pop
git stash drop
-------------------------------------------------
🔟 Undo & Recovery
Working Directory
git restore file.txt
Staging Area
git restore --staged file.txt
Commits
git reset --soft HEAD~1
git reset --mixed HEAD~1
git reset --hard HEAD~1
git revert <commit>
---------------------------------------------------
1️⃣1️⃣ Tags (Releases)
git tag
git tag v1.0
git push origin v1.0
git push --tags
---------------------------------------------
1️⃣2️⃣ Cherry Pick (Advanced)
Copy one commit from another branch
git cherry-pick <commit-hash>
---------------------------------------------------
1️⃣3️⃣ Reflog (Life Saver )
Recover lost commits
git reflog
git reset --hard <hash>
-----------------------------------------------------
1️⃣4️⃣ Bisect (Bug Hunting )
Binary search for broken commit
git bisect start
git bisect bad
git bisect good <commit>
git bisect reset
---------------------------------------------------
1️⃣5️⃣ Interactive Rebase
git rebase -i HEAD~5
Actions:

pick
reword
squash
drop
--------------------------------------------------------
1️⃣6️⃣ Submodules
git submodule add URL
git submodule init
git submodule update
--------------------------------------------------------
1️⃣7️⃣ Subtree
git subtree add --prefix=dir URL main
git subtree pull --prefix=dir URL main
------------------------------------------------------------
1️⃣8️⃣ Worktree
git worktree add ../new-dir branch-name
--------------------------------------------------------------
1️⃣9️⃣ Maintenance & Cleanup
git gc
git fsck
git prune
git clean -f
git clean -fd
------------------------------------------------------------------

