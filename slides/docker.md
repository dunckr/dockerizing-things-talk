### Dockerfile

brew install docker


## Tips

Run only one process per container
Minimize the number of layers
Sort multi-line arguments


Build cache
During the process of building an image Docker will step through the instructions in your Dockerfile executing each in the order specified. As each instruction is examined Docker will look for an existing image in its cache that it can reuse, rather than creating a new (duplicate) image. 


