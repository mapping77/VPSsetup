# VPSsetup
This is a backup of setting up a new vps based on shadowsocks-libev, which originates from solving the problem of visiting google scholar. It includes the basic steps of seting up a simple vps for a beginer. It will also be used to be a record for the problems that I have met, solved and need-to-be solved during the usage of this.
## Vultr+Debian9+shadowsocks-libev+serverspeeder
1. It will be better to choose Japan or Singapore server locations for lower ping value.
2. It is not recommented for you to new a vps from snapshot taked in a different location because there may be a problem of ip configuration.
3. Using ssh connecting to the vps and install the shadowsocks-libev.(Be careful about that y default sudo is not installed on Debian.)
https://github.com/shadowsocks/shadowsocks-libev#debian--ubuntu
https://unix.stackexchange.com/questions/354928/bash-sudo-command-not-found
```
sudo sh -c 'printf "deb http://deb.debian.org/debian stretch-backports main" > /etc/apt/sources.list.d/stretch-backports.list'
sudo apt update
sudo apt -t stretch-backports install shadowsocks-libev
```
## Shadowsocks-libev basics
```
service shadowsocks-libev status
service shadowsocks-libev start
service shadowsocks-libev stop
service shadowsocks-libev restart
```
You can find the config.json on `/etc/shadowsocks-libev/config.json`,and use scp to back it up on your local computer` scp root@server_ip:/etc/shadowsocks-libev/config.json ~/backupconfig/`
```
{
    "server":"server_ip",
    "server_port":server_port,
    "local_port":1080,
    "password":"passwords of ss",
    "timeout":600,
    "method":"aes-256-cfb"
}
```
## Serverspeder
Need to be added.
