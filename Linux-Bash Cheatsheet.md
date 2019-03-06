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

## File Viewer
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