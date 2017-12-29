# Git Commands
Collection of useful Git Commands

## Adding a file to the previous commit - [Source](https://stackoverflow.com/questions/40503417/how-to-add-a-file-to-the-last-commit-in-git?answertab=oldest#tab-top)
```
git add the_left_out_file
git commit --amend --no-edit
```
The --no-edit flag allow to make amendment to commit without changing commit message.


## Deleting old local branches -  [Source](http://erikaybar.name/git-deleting-old-local-branches/)
```
git branch -vv | grep 'origin/.*: gone]' | awk '{print $1}' | xargs git branch -d  
```
* **Prune remote branches** : Deletes all stale branches that have already been removed from the remote repository but are still locally available in "remotes/"
```
git remote prune origin 
```
* **List local git branches**
```
git branch -vv
```
* **Filter git branches down to only those with deleted upstream/remote counterparts**
```
grep 'origin/.*: gone]'
```
* **Pluck out branch names from output**
```
awk '{print $1}'
```
* **Delete the branches**
```
xargs git branch -d
```
* **Review/edit list before deleting**
```
pbcopy
```

## Finding a bad git commit [Source](https://robots.thoughtbot.com/git-bisect)
```
git bisect bad
```

## Recovering lost commits [Source](http://gitready.com/intermediate/2009/02/09/reflog-your-safety-net.html)
```
git reflog
```
