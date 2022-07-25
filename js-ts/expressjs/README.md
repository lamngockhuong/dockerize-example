## I. On-premises
Install dependencies:
```
$ npm install
```

On MacOS or Linux, run the app with this command:
```
$ DEBUG=expressjs:* npm start
```

On Windows Command Prompt, use this command:
```
> set DEBUG=expressjs:* & npm start
```

On Windows PowerShell, use this command:
```
PS> $env:DEBUG='expressjs:*'; npm start
```
## II. Docker - Docker compose
### Docker
Build expressjs image
```
$ cd js-ts/expressjs/
$ docker build -t dockerize-example/expressjs:v1 .
```

Run the application on docker:
```
$ cd js-ts/expressjs/
$ docker run -d \
--name dockerize-expressjs \
-p 3000:3000 \
dockerize-example/expressjs:v1
```
With DEBUG:
```
$ cd js-ts/expressjs/
$ docker run -d \
--name dockerize-expressjs \
-p 3000:3000 \
-e DEBUG=expressjs:* \
dockerize-example/expressjs:v1
```

### Docker compose
Run the application:
```
$ cd js-ts/expressjs/
$ docker compose up
```

Additional:
```
$ docker compose -f docker-compose.prod.yml up
```

Stop:
```
$ cd js-ts/expressjs/
$ docker compose stop
```

*Note:
By making a bind mount `./:/app`, we are completely overriding the .dockerignore. Since the bind mount it attached after the image is build, even files that were ignored are now mounted to the container. A better way to use bind mounts is to map specific files or folders.
(Refer to: https://medium.com/nerd-for-tech/bigger-dockerignore-smaller-docker-images-49fa22e51c7)
```
volumes:
  - ./:/app
```
