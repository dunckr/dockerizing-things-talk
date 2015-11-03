## Docker Optimised [](images/engine.svg)

```sh
FROM node:4.2

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y \
        apt-transport-https \
        inotify-tools \
        build-essential \
        sudo \
        curl \
        libfreetype6 \
        libfontconfig1

RUN npm install -g phantomjs nodemon

ADD package.json /tmp/package.json
RUN cd /tmp && npm install
RUN mkdir -p /app && cp -a /tmp/node_modules /app/

ADD . /app
WORKDIR /app

CMD npm start
```

+ Cache
+ Combine lines

note:
  Run only one process per container
  Minimize the number of layers
  Sort multi-line arguments
  Build cache and invalidate it
  During the process of building an image Docker will step through the instructions in your Dockerfile executing each in the order specified. 
  Check for existing image in its cache 
