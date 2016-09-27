# Firewalld
Bash script to manage iptables rules

## Instalation and configuration
* Copy the file `firewalld` into `init.d/` directory
* Copy the config file `firewall.conf` into `/etc` directory
* Add some rules to config file

```
    # -*-Shell-script-*-
    IPT="/sbin/iptables"
    
    # Accept ping
    $IPT -A INPUT -p icmp -j ACCEPT
    
    # Accept connectios to HTTP and HTTPS ports
    $IPT -A INPUT -p tcp --dport 80 -j ACCEPT
    $IPT -A INPUT -p tcp --dport 443 -j ACCEPT
    
    # Accept stablished connections
    $IPT -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
```

## Start the service
```
    $ /etc/init.d/firewalld start
```

## Stop the service
```
    $ /etc/init.d/firewalld start
```
