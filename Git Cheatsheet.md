# Git Cheatsheet


## Stash & Discard everything, then reset

```
git checkout -- .  (or replace . with filename)
git reset --hard
```

## Store Username/Password
```
git config credential.helper store
```

## Get from origin master
```
git pull origin master
```

## Apply Patch File
```
git apply -v path/to/patch/patchfile.patch
```

