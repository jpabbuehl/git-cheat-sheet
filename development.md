# Bring back a file from previous time to current project timeline
# Needs to commit
git checkout <commit-hash> -- <filepath>
git add .
git commit -m '<message>'
git push

# In order to remove changes for a file from the previous commit, do the following:
git checkout HEAD^ <filepath>
git add <filepath>
git commit --amend --no-edit

then

# if not pushed
git reset --soft HEAD@{1}

# if pushed, safe and will create an extra commit to undo
git revert <bad commit>

# if pushed, rewrite git history (risky if someone already pulled)
git reset HEAD^ --hard
git push --force-with-lease [remote] [branch]
