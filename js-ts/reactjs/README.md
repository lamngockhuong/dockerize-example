## I. On-premises
+ Run the app on dev:
```
$ npm start
```

To test that the application is working properly, access to http://localhost:3000

## II. Docker - Docker compose
### Docker
+ Build reactjs image
```
$ cd js-ts/reactjs
$ docker build -t dockerize-example/reactjs:v1 .
```

+ Run our container:
```
$ cd js-ts/reactjs
$ docker run --rm -d \
--name dockerize-reactjs \
-p 3000:3000 \
dockerize-example/reactjs:v1
```

### Docker compose

+ Run the application:
```
$ cd js-ts/reactjs
$ docker compose -f docker-compose.dev.yml up --build
```

+ Stop:
```
$ cd js-ts/reactjs
$ docker compose -f docker-compose.dev.yml stop
```
