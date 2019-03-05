# Linux/BASH Cheatsheet


## Create Tarball of Directory Tree (root of file)

```
tar -zcf ~/file.tar.gz -C /path/to/directory .
```

## Make directories, >1 level deep

```
mkdir -p create/all/these/directories
```

## Global JAVA_HOME

`nano /etc/profile.d/java_home.sh`

```
export JAVA_HOME=/usr/lib/jvm/jre-openjdk
```

## find process by user name
```
ps -aux | grep PROCESSNAME
```

## find process id by process name
```
pidof PROCESSNAME
```