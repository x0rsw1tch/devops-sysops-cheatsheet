# Letsencrypt Cheatsheet


### Create pkcs12 Certificate package from LE Certificate Files
```
openssl pkcs12 -export -out ~/certificate.pfx -inkey /etc/letsencrypt/live/example.com/privkey.pem -in /etc/letsencrypt/live/example.com/cert.pem -certfile /etc/letsencrypt/live/example.com/chain.pem
```

### Set Manual Mode with ACME Server, for getting wildcard certifcates
```
certbot certonly --manual --server https://acme-v02.api.letsencrypt.org/directory -d *.example.com
```