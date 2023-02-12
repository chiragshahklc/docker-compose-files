# traefik
[traefik](https://traefik.io/traefik/) is a reverse proxy. We can use this with a docker too. You can find documentation [here](https://doc.traefik.io/traefik/).

## Initial setup
We have configure traefik with `traefik.yml` file inside a docker.
For how to supply this **config** to traefik container please check **traefik.yml** in Prerequisite section.

## Prerequisite
### docker network
Given `docker-compose.yml` file expects network name **internal-net** to be already exist in your docker environment.

You can check if your network exist or not with following command
```bash
$ docker network ls
```

If your network doesn't exist, you can create one with following command
```bash
# this will create a bridge network
$ docker network create internal-net
```
### docker volume
Given `docker-compose.yml` file expects directory called `/Users/admin/docker_volumes/traefik` to exist.

If you don't have that directory available, please create one directory for your docker volume and replace the path in `docker-compose.yml` file.

### traefik.yml
- `traefik.example.yml` file has already given.
- Create `traefik.yml` file inside `/Users/admin/docker_volumes/traefik` directory.
- We have already configured **traefik_config** volume with container which will take `traefik.yml` which we have created.
## Run your container
Following command will run your portainer container
```bash
$ docker compose up -d
```