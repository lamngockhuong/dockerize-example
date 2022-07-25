## I. On-premises
+ Run the app on dev:
```
$ ./mvnw spring-boot:run
```
+ Run the app on stg/prod:
```
$ ./mvnw package && java -jar target/spring-petclinic-2.7.0-SNAPSHOT.jar
```

To test that the application is working properly, access to http://localhost:8080

## II. Docker - Docker compose
### Docker
+ Build spring-petclinic image
```
$ cd java-k
otlin/spring-petclinic
$ ./mvnw package
$ docker build -t dockerize-example/spring-petclinic:v1 .
```

+ Run our container:
```
$ cd java-k
otlin/spring-petclinic
$ docker run --rm -d \
--name dockerize-spring-petclinic \
-p 8080:8080 \
dockerize-example/spring-petclinic:v1
```

### Docker compose
+ Run MySQL & Postgre:
```
$ cd java-k
otlin/spring-petclinic
$ docker compose up
```

+ Run the application:
```
$ cd java-k
otlin/spring-petclinic
$ docker compose -f docker-compose.dev.yml up --build
```

+ Stop:
```
$ cd java-k
otlin/spring-petclinic
$ docker compose -f docker-compose.dev.yml stop
```

## References
+ https://github.com/spring-projects/spring-petclinic
