## Docker Optimised [](/images/engine.svg)
```
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
  Build cache
  During the process of building an image Docker will step through the instructions in your Dockerfile executing each in the order specified. As each instruction is examined Docker will look for an existing image in its cache that it can reuse, rather than creating a new (duplicate) image. 
