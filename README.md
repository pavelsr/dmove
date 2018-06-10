# dmove - Docker move utilities set

Set of utilities for fast trasfer dockerized apps to new VDS

Including:

`move-volume` - move all docker volumes of selected containers (transfer data gzipped)

`move-db` - move sql-like database

`dmove-copy-id` - wrapper under ssh-copy-id, reads hostname from config file

`dmove-config` - generate new config file (conenient if you need to have separate REMOTE_HOST perl user)

`dmove-nginx-proxy` - quick deployment of [nginx-proxy](https://github.com/jwilder/nginx-proxy) container

Config file: `~/.dmove`

# Installation

```
curl -sSL https://raw.githubusercontent.com/pavelsr/dmove/master/install-dmove | sudo bash
```

Just dmove-nginx-proxy:

```
sudo wget https://raw.githubusercontent.com/pavelsr/dmove/master/install-dmove-nginx-proxy -O /usr/local/bin/dmove-nginx-proxy && sudo chmod +x /usr/local/bin/dmove-nginx-proxy
```
