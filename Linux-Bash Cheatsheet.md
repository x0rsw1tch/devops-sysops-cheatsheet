# Linux/BASH Cheatsheet


## Handling Files

### Create Tarball of Directory Tree (root of file)

```
tar -zcf ~/file.tar.gz -C /path/to/directory .
```

### Make directories, >1 level deep

```
mkdir -p create/all/these/directories
```

### Show disk usage per directroy (recursive)
```
du -sh .
```

### Clone Directory
```
cp -R dirtocopy/ newdir/
```

### Display Directory Tree
```
tree -d -L 1
```
> `-d`: Only show directories
> `-L`: Determines how many levels deep to traverse

### Display 10 biggest files in directory
```
du -sk * | sort -nr | head -10
```
> `du -sk *`: Lists file sizes followed by file name
> `sort -nr`: Sort by size (descending)
> `head -10`: Only show top 10

### Show last modified files recursively
```
find . -type f -printf '%T@ %p\n' | sort -n | tail -1 | cut -f2- -d" "
```

### Show total size of directory
```
du -cah | grep total
```

### Get the last 5 listings in a directory,  _in descending order (-r) by date (-t)_
```
ls -ltr | head -5
```
### Find text in file
> In root of search dir:
```
grep -lir "{search}"
```
> e.g.: `grep -lir "@todo"`


### File Viewer
```
less path/to/file
```
> You can also pipe text output to `less`, eg: cat error.log | grep SEVERE | less


### Download File from world-wide-web
```
curl -O https://www.example.com/path/to/file.tar.gz
```
> or use `wget https://www.example.com/path/to/file.tar.gz`


### find and replace string in file (be careful!). Full Line Replace
```
sed -i "/String to replace/c Replaced text" path/to/file
```

### Create file and/or update file mod date
```
touch /path/to/file
```

### Create Symbolic Link
```
ln -s /point/to/here name_of_symlink
```
> Note: You can replace name_of_symlink with `.` to just use the target path directory name


### Remove (Symbolic) Link
```
unlink /path/to/link
```

<hr>


## Environment Variables

### Global JAVA_HOME

`nano /etc/profile.d/java_home.sh`

```
export JAVA_HOME=/usr/lib/jvm/jre-openjdk
```

<hr>


## Process Management

### Find process by user name
```
ps -aux | grep PROCESSNAME
```

### Find process id by process name
```
pidof PROCESSNAME
```

### Show live process and hardware manager
```
top
```
> or use `htop` for a better TUI

### Show free RAM
```
free -m
```

### Show Apache Owner
```
ps aux | grep -E '[a]pache|[h]ttpd|[_]www|[w]ww-data|[n]ginx' | grep -v root | head -1 | cut -d\  -f1
```

<hr>


## Disk Management

### Show Mount Point Utilization
```
df -h
```

### Show Partition UUID
```
lsblk -f
```

<hr>


## Misc

### Virtual Console `screen`


### Run Application in virtual named console
```
screen -S VirtualConsoleName /path/to/program
```
> Use Ctrl+A, d to detach window 
> Reattach to Virtual Console: `screen -r VirtualConsoleName` 
>  List all Virtual Consoles (only lists for current user): `screen -r`