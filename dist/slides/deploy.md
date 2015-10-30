## Deploy

```sh
docker-machine create \
  --driver digitalocean \
  --digitalocean-access-token your-digitalocean-api-token \
  --digitalocean-size 2gb \
  dobox
```

```sh
eval "$(docker-machine env dev)"
```

```sh
docker-compose up -d
```
