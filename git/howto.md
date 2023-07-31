# Git HowTos

## Reset commit history 

Sometimes I don't care about commit history and want to remove all of it. 

There are two options:

1) Create a new orphan branch and replace the branch with it

```shell
# Create an orphan branch
git checkout --orphan tmp_branch
git add -A
git commit -m "Initial Commit"

# Deletes the master branch
git branch -D master  

# Rename the current branch to master
git branch -m master  

# Force push master branch to origin
git push -f origin master  

# optional, remove the old files
git gc --aggressive --prune=all
```

2) Remove .git folder and re-push it

```shell
# Remove .git folder
rm -rf .git

# recreate the repo
git init
git add .
git commit -m "Initial commit"

# push to github 
git remote add origin git@github.com:<YOUR ACCOUNT>/<YOUR REPOS>.git
git push -u --force origin master
```

