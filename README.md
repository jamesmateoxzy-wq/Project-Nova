*****Project Nova: Part 2, Troubleshooting & Emergency Fixes*****

1. The "Oops, wrong file" Problem
Command:
git restore --staged .env
Explanation: This unstages .env while keeping the file and its local changes intact.

2. The "Typo in the message" Problem
Command:
git commit --amend -m "Fixed authentication typo"
Explanation: This changes the most recent commit message without creating a new commit. This is appropriate because the commit has not been pushed yet.

3. The "Forgot a file" Problem
Commands:
git add styles.css
git commit --amend --no-edit
Explanation: This stages styles.css and adds it to the previous commit without changing the commit message.

4. The "I hate these changes" Problem
Command:
git restore index.html
Explanation: This discards the unstaged local changes in index.html and restores the version from the last commit.

5. The "Wrong Branch" Problem
Commands:
git branch new-feature
git reset HEAD~3 --hard
git checkout new-feature
Explanation: This creates a new branch pointing to the current commits, moves main back by three commits, and switches to new-feature. The --hard option permanently discards uncommitted changes, so this should only be used when the working tree is safe.

6. The "Detached HEAD" Problem
Command:
git switch -c recovery-branch
Explanation: This creates a new branch at the current commit, preserving the commits made while in detached HEAD state.

7. The "Undo a pushed mistake" Problem
Command:
git revert <buggy-commit-hash>
Explanation: This creates a new commit that reverses the changes introduced by the buggy commit, preserving the shared history.

8. The "Accidental Deletion" Problem
Commands:
git reflog
git branch <deleted-branch-name> <commit-hash>
Explanation: git reflog helps locate the deleted branch's last commit. The second command recreates the branch at that commit.

9. The "Ghost Files" Problem
Command:
git add -u
Explanation: This stages tracked-file changes, including deletions, for the next commit.

10. The "Pushed to the void" Problem
Command:
git push origin --delete testing-junk
Explanation: This deletes the testing-junk branch from the remote GitHub repository. It does not delete a local branch with the same name.
