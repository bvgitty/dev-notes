# Day 07 notes

# Things covered in Undo lab
- git restore - throws away an edit
- git restore --staged -unstages but keeps the edit
- git commit --amend ( doesnt edit a commit but replaces it with a new commit)
- git commit --amend --no-edit ( keeps the message)
- git stash = park unfinished work
- git stash pop (apply reverses but keeps a copy in the list)
- git stash list
- reset - only for local commits
    - Soft
    - Mixed
    - hard
- revert - for pushed commits as it adds to history
- Reset vs. revert, in one line: reset rewrites history (only for local commits), and revert adds to history (safe for shared commits).
- reflog
- rebase
    - git rebase -i HEAD~4 (Top 4 commits/reverse order)
    - pick - keep the commits as is
    - Squash - combine the message
    - drop - delete the commit
    - reword - edit the message
    - fixup - sqaush and throw the message
-  git rebase --abort - puts everything back