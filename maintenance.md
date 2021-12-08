# Get latest short commit hash in current branch
git rev-parse --short HEAD

# Set branch to specific commit hash
# Current  branch is checked and there is no uncommited changes that you want to keep
# use case: revert a branch to a previous commit, to trigger redeployment
git reset --hard <commit-hash>
git push -f origin <branch>

## Find branch name on local and remote by regex
git branch --all --list 'feature*'

# remove sensitive data committed and pushed accidentally
(feature-branch)$ git rm --cached sensitive_file
echo sensitive_file >> .gitignore
(feature-branch)$ git add .gitignore
(feature-branch)$ git commit --amend --no-edit
(feature-branch)$ git push --force-with-lease origin [branch]
`
