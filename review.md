## Check files about to be pushed to origin
git diff --stat --cached <branch>

# revert an unfinished feature branch that was merged to early to develop
git revert -m 1 <commit-hash>
`
