# dmove - Docker move utilities set

Set of utilities for fast trasfer dockerized apps to new VDS

Including:

`dmove` - full auto transfer (image, its volumes, network settings)

`move-container` - transfering container as image to new host

`move-volumes` - move all docker volumes of selected containers (transfer data gzipped).

`move-db` - move sql-like database

*`move-db` and `move-volume` by default doesn't make deployment, they just trasfer appropriate files to `$REMOTE_FOLDER`*

*To deploy you need to specify image name on target host in addition to container name*

`<move-volumes|move-db> $CONTAINER_NAME <author/image_tag> <network_to_connect>`

`move-db` has two additional arguments:

`hostname`

`do_pwd_sql_volume` (works for `/var/lib/mysql`)

`<move-db $CONTAINER_NAME <author/image_tag> <network_to_connect> <hostname_to_apply> <do_pwd_sql_volume>`

Related utils:

`dmove-copy-id` - wrapper under ssh-copy-id, reads hostname from config file

`dmove-config` - generate new config file (conenient if you need to have separate REMOTE_HOST perl user)

`dmove-nginx-proxy` - quick deployment of [nginx-proxy](https://github.com/jwilder/nginx-proxy) container

Config file: `~/.dmove`


# Requirements

[jq](https://stedolan.github.io/jq/)

REMOTE_HOST (remote) user must have privileges to run docker

Docker must be installed on both machines

# Installation

```
curl -sSL -H 'Cache-Control: no-cache' https://raw.githubusercontent.com/pavelsr/dmove/master/install-dmove | sudo bash
```

Just dmove-nginx-proxy:

```
sudo wget https://raw.githubusercontent.com/pavelsr/dmove/master/dmove-nginx-proxy -O /usr/local/bin/dmove-nginx-proxy && sudo chmod +x /usr/local/bin/dmove-nginx-proxy
```

# Used naming conventions

On new host container will be started with same name as at old

# Recommended docker objects naming conventions to use dmove without problems

`_db` : container name for app `<example>` must be `<example_db>`

## See more

Similar project: https://github.com/tubesandlube/blimp
