# cURL Cheatsheet

### Download File from world-wide-web
```
curl -O https://www.example.com/path/to/file.tar.gz
```
---

### Send authentication
```
curl --user 'username:password' --basic
curl --user 'username:password' --digest
```


### show HTTP Headers Only
```
curl -vI https://www.example.com/
```
---


### WebDAV: Create Directory
```
curl --user "username:password" -X MKCOL https://example.com/newfolder
```
---

### Use Bearer Token for requests (JWT)
```
curl -H "Authorization: Bearer TOKEN" https://www.example.com/
```
---