## docker-compose ![](images/compose.svg)

docker-compose.yml

```sh
brew install docker-compose
```

```sh
nginx:
  build: nginx/
  ports:
   - "443:443"
   - 80:80
  links:
   - web
web:
  build: .
  ports:
   - "8000:8000"
  volumes:
   - .:/code
  links:
   - mongo
mongo:
  image: mongo
```
