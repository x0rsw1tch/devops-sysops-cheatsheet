# Git Cheatsheet


### Stash your files
```
git stash save "a meaningful name"
```
---

### Stash & Discard everything, then reset

```
git checkout -- .  (or replace . with filename)
git reset --hard
```
---


### Windows Line Break nonsense
```
git config core.filemode false
git config core.autocrlf true
```


### Store Username/Password
```
git config credential.helper store
```
---


### Get from origin master
```
git pull origin master
```
---


### Apply Patch File
```
git apply -v path/to/patch/patchfile.patch
```

