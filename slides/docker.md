## Dockerfile ![](/images/engine.svg)

```
brew install docker
```

```
FROM node:4.2

RUN apt-get update

RUN npm install nodemon -g

ADD . /app
RUN npm install

CMD npm start
```

+ Order matters
+ ADD and COPY are NOT the same

note:
  other commands
  difference between add and run
