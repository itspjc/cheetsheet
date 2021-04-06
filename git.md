# Cheetsheet for Git

### Create branch
```
git checkout -b feature-01 # create local branch
git push origin feature-01 # create remote branch
git branch --set-upstream-to origin/feature-01 # connect local with remote branch
```

### Delete branch
```
git checkout develop # 다른 브랜치로 이동
git branch --delete feature-01 # delete local branch
git branch -D feature-01 # delete local branch forcely
git push origin :feature-01 # delete remote branch
```

### Merge branch
```
git checkout master
git merge feature/XXX
```

### Merge Conflict
```
git fetch origin master
git checkout feature/XXX
get merge FETCH_HEAD

-> resolve the merge conflicts

git commit 
git push origin HEAD
```

### Deleted remote branch still visible problem
```
git remote prune origin
git branch -d -r origin/coolbranch
```
