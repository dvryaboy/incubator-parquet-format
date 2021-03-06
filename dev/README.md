# Parquet Developer Scripts
This directory contains scripts useful to developers when packaging,
testing, or committing to Parquet.

Merging a pull request requires being a committer on the project.

* How to merge a Pull request:
have an apache and apache-github remote setup
```
git remote add apache-github git@github.com:apache/incubator-parquet-format.git
git remote add apache https://git-wip-us.apache.org/repos/asf/incubator-parquet-format.git
```
run the following command
```
dev/merge_parquet_pr.py
```

Note:
* The parent directory of your parquet repository must be called parquet-format
* Without jira-python installed you'll have to close the JIRA manually

example output:
```
Which pull request would you like to merge? (e.g. 34):
```
Type the pull request number (from https://github.com/apache/incubator-parquet-format/pulls) and hit enter.
```
=== Pull Request #X ===
title	Blah Blah Blah
source	repo/branch
target	master
url	https://api.github.com/repos/apache/incubator-parquet-format/pulls/X

Proceed with merging pull request #3? (y/n): 
```
If this looks good, type y and hit enter.
```
From git-wip-us.apache.org:/repos/asf/incubator-parquet-format.git
 * [new branch]      master     -> PR_TOOL_MERGE_PR_3_MASTER
Switched to branch 'PR_TOOL_MERGE_PR_3_MASTER'

Merge complete (local ref PR_TOOL_MERGE_PR_3_MASTER). Push to apache? (y/n):
```
A local branch with the merge has been created.
type y and hit enter to push it to apache master
```
Counting objects: 67, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (26/26), done.
Writing objects: 100% (36/36), 5.32 KiB, done.
Total 36 (delta 17), reused 0 (delta 0)
To git-wip-us.apache.org:/repos/asf/incubator-parquet-format.git
   b767ac4..485658a  PR_TOOL_MERGE_PR_X_MASTER -> master
Restoring head pointer to b767ac4e
Note: checking out 'b767ac4e'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by performing another checkout.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -b with the checkout command again. Example:

  git checkout -b new_branch_name

HEAD is now at b767ac4... Update README.md
Deleting local branch PR_TOOL_MERGE_PR_X
Deleting local branch PR_TOOL_MERGE_PR_X_MASTER
Pull request #X merged!
Merge hash: 485658a5

Would you like to pick 485658a5 into another branch? (y/n):
```
For now just say n as we have 1 branch
