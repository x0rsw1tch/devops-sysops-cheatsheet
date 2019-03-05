# SELinux Cheatsheet

## Disable and log all violations
```
setenforce Permissive
```

## List SELInux Booleans
```
semanage boolean -l
```
With Explanation
```
getsebool -a
```

## Change security context, accepts wildcards
```
semanage fcontext -a -t context_name /path
```

## Commits change from fcontext (use -r for recursive)
```
restorecon -v /path
```

## SELinux Audit Log
```
/var/log/audit/audit.log
```

## Show SELinux audit summary
```
aureport -a
```

## Show SELinux roles
```
seinfo -r
```

## Show processes with Security Contexts
```
ps -eZ
```

## Allow Apache to connect to local host (reverse proxy)
```
setsebool -P httpd_can_network_connect 1
```


## Allow Apache to connect to DB over TCP
```
setsebool -P httpd_can_network_connect_db 1
```

## Allow Apache to host in samba context
```
setsebool -P httpd_use_cifs 1
```


## Allow chrooted ssh to read write to home
```
setsebool -P ssh_chroot_rw_homedirs 1
```

