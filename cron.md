# Cron Cheatsheet

### Show crontab file for current user
```
crontab -e
```


### Show all cron jobs for all users
```
cat /etc/passwd | sed 's/^\([^:]*\):.*$/crontab -u \1 -l 2>\&1/' | grep -v "no crontab for" | sh
```
