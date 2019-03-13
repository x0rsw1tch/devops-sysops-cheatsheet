# Linux Filesystem Permissions

### Change permissions of directories only
```
find -type d | xargs chmod 775
```

### Change permissions of files only
```
find -type f | xargs chmod 664
```

### Change owner/group recursively
```
chown -R user:group dir
```

### Add Specific Permission Type Recursively
```
Add USER read: chmod -R u+r .
Add GROUP read: chmod -R g+r .
Add ALL read: chmod -R o+r .

Add USER write: chmod -R u+w .
Add GROUP write: chmod -R g+w .
Add ALL write: chmod -R o+w .

Add USER execute: chmod -R u+x .
Add GROUP execute: chmod -R g+x .
Add ALL execute: chmod -R o+x .
```

### Update file permissions for any file matching a certain extension
```
find -iname *.css -print0 | xargs -0 chmod 775
```




### Show ACL Permissions
```
getfacl /path/to/dir
```

### Set ACL Permissions

Set Default Group Bit: `chmod -R g+s /path/to/dir`
Set New File/Directory Mask: `setfacl -dRm u::rwx,g::rwx,o::rx /path/to/dir`

> Note: ext4 and most other file systems ignore owner mask for some reason