## I. On-premises

+ Run the app with this command:
```
$ go run main.go
```

To test that the application is working properly, access to http://localhost:8080

## II. Docker - Docker compose
### Docker
+ Build docker-gs-ping image
```
$ cd go/docker-gs-ping/
$ docker build -t dockerize-example/docker-gs-ping:v1 .
```

+ Run our container:
```
$ cd go/docker-gs-ping/
$ docker run --rm -d \
--name dockerize-docker-gs-ping \
-p 8080:8080 \
dockerize-example/docker-gs-ping:v1
```

### Docker compose
+ Run the application:
```
$ cd go/docker-gs-ping/
$ docker compose -f docker-compose.dev.yml up --build
```

+ Stop:
```
$ cd go/docker-gs-ping/
$ docker compose -f docker-compose.dev.yml stop
```

## References
+ https://github.com/olliefr/docker-gs-ping
