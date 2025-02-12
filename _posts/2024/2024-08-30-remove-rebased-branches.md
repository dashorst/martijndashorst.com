---
layout: post
status: published
published: true
title: "List (and delete) git branches that have been rebased and merged"
---
Whenever you rebase and merge a branch, git will not discover the local
branch as being merged. So as I use ticket numbers as branch names and
use the ticket number in the commit summary (together with a more
descriptive summary and body) I can use the log to see if a branch was
merged.

The following oneliner bash script below will check if the branch name 
exists in the log of the current branch (usually main) and generate
corresponding delete branch git calls.

```bash
git for-each-ref --format='%(refname:short)' refs/heads | grep -v main | while IFS= read -r branch; do
    if [[ $(git log -1 --grep "$branch") ]]; then
        echo "git branch -D $branch"
    fi
done
```

So given a local branch with name `JIRA-banana`, and a commit with a 
message like `JIRA-banana fixed NPE in FooBar` which was rebased and merged
with main, so the local head commit(s) don't match with what was merged,
this will show the branch as merged.

In a single line command:
```bash
git for-each-ref --format='%(refname:short)' refs/heads | grep -v main | while IFS= read -r branch; do if [[ $(git log -1 --grep "$branch") ]]; then echo "git branch -D $branch" ; fi ; done
```

Output:
```
git branch -D JIRA-banana
```
