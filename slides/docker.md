## Dockerfile ![](images/engine.svg)

```sh
brew install docker
```

```sh
FROM node:4.2

RUN apt-get update

RUN npm install nodemon -g

ADD . /app
RUN npm install

CMD npm start
```

+ Order matters
+ Containers are made up of layers
+ Results are committed like version control

note:
  save time reading the docs
  best practises
