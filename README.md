# tkrzw-docker 

## SYNOPSYS

```sh
# build image
docker build tkrzw-rpc --tag tkrzw-rpc

# start TinyDBM daemon
docker run --name tkrzw-rpc -p 1978:1978 tkrzw-rpc tkrzw_server --log_level debug

# connect local
docker exec tkrzw-rpc tkrzw_dbm_remote_util set one first
docker exec tkrzw-rpc tkrzw_dbm_remote_util get one

# connect via Docker for Mac
docker run tkrzw-rpc tkrzw_dbm_remote_util set --address host.docker.internal:1978 two second
docker run tkrzw-rpc tkrzw_dbm_remote_util get --address host.docker.internal:1978 two
```

## LINKS

- https://dbmx.net/tkrzw
- https://github.com/estraier/tkrzw
- https://github.com/estraier/tkrzw-rpc
- https://github.com/kawanet/tkrzw-docker
