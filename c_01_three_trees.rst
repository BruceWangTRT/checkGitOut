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
1. move a file from Working Directory to Index
  1.1 what if the file is untracked? Does it make a difference?
  1.2 what if the file was already modified in Index
    1.2.1 and there is no conflict
    1.2.2 and there are conflicts
  1.3 what if the file is removed from Working Directory
2. move a file from Index to Working Directory
  2.1 what if the file was modified again in Working Directory?
    2.1.1 and there is no conflict
    2.1.2 and there are conflicts
  2.2 what if the file was removed in Working Directory?
  2.3 what if the file was removed in Index?
3. move a file from Index to HEAD
4. move a file from HEAD to Index
5. move a file from Working Directory to HEAD
6. move a file from HEAD to Working Directory
