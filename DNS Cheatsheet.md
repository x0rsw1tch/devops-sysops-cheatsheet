# DNS Cheatsheet


## dig Cheatsheet

### Query Default DNS server for record
```
dig exmaple.com
```

### Query Specific DNS server for record
```
dig @1.1.1.1 exmaple.com
```

### Query Specific DNS server for specific record
```
dig -t TXT example.com
```
