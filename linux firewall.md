# Linux Firewall Cheatsheet

### Open incoming port

iptables: `iptables -A INPUT -p tcp --dport 80 -j ACCEPT`

firewalld: `firewall-cmd --zone=public --permanent --add-port=80/tcp`
---


### Save Firewall rules
iptables init.d: `iptables-save`

iptables systemd: `service iptables save` (Needs package iptables-services)
---