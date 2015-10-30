## docker-machine ![](images/machine.svg)

```sh
brew install docker-machine
```

```sh
docker-machine create --driver virtualbox --virtualbox-memory 3076 dev
docker-machine start dev
eval "$(docker-machine env dev)"
```

```sh
CURRENT_DIRECTORY := $(shell pwd)

build:
	@docker-compose build

start:
	@docker-compose up -d

stop:
	@docker-compose rm -f
	@docker-compose stop

status:
	@docker-compose ps
	@docker-compose logs

cli:
	@docker-compose run --rm web bash

.PHONY: start stop status cli
```
