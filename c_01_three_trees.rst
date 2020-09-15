*********
Git Trees
*********

Git as a system manages and manipulates three trees in its normal operation:

+-------------------+-----------------------------------+
| Tree              | Role                              |
+===================+===================================+
| HEAD              | Last commit snapshot, next parent |
+-------------------+-----------------------------------+
| Index             | Proposed next commit snapshot     |
+-------------------+-----------------------------------+
| Working Directory | Sandbox                           |
+-------------------+-----------------------------------+


***********
Chanllenges
***********

Know your way around

1. What is HEAD pointing to?
  1.1 what is detached HEAD?
2. What has been modified in working directory, compared to Index?
3. What has been modified in working directory, compared to HEAD?
4. What has been modified in Index, compared to HEAD?
5. What if you are in middle of a rebase? How could you tell?
6. What if you are in middle of a merge? How could you tell?
7. Is current branch tracing a remote branch?
  7.1 Is current branch up to date with the remote branch?
8. Is there any stash?
  8.1 How to tell which stashes might be relevant to your branch?


Move a file (or its states rather) between two trees:

1. from Working Directory to Index
  1.1 what if the file is untracked? Does it make a difference?
  1.2 what if the file was already modified in Index
    1.2.1 and there is no conflict
    1.2.2 and there are conflicts
  1.3 what if the file is removed from Working Directory
2. from Index to Working Directory
  2.1 what if the file was modified again in Working Directory?
    2.1.1 and there is no conflict
    2.1.2 and there are conflicts
  2.2 what if the file was removed in Working Directory?
  2.3 what if the file was removed in Index?
3. from Index to HEAD
4. from HEAD to Index
5. from Working Directory to HEAD
6. move a file from HEAD to Working Directory


*******
Answers
*******

Know your way around

1. :code:`git status` or :code:`cat .git/HEAD`
  1.1 HEAD normally points to a branch. When it points to a commit, git is in a detached HEAD mode.
2. :code:`git status` shows the file names, :code:`git diff` shows the actual modifications
3. :code:`git status` shows the file names, :code:`git diff HEAD` shows the actual modifications
4. :code:`git status` shows the file names, :code:`git diff --cached` shows the actual modifications
5. :code:`git status` tells you that a *rebase is in progress* together with branch information and conflicts. Also, if configured, your prompt will show you something like :code:`(git)-[branch-name|rebase]`
6. :code:`git status` tells you that you have *unmerged paths* . Also, if configured, your prompt will show you something like :code:`(git)-[branch-name|merge]`
7. :code:`git status` tells you the difference between your local branch and remote branch if tracking one (shown in commits). It says nothing if not tracking any remote branch.
  7.1 :code:`git status` tells you that already
8. :code:`git stash list` shows all the stash entries.
  8.1 By default a stash is named like *WIP on branchname*
