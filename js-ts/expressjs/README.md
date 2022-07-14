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
## Docker - Docker compose
### Docker
Build expressjs image
```
$ docker build -t dockerize-example/expressjs:v1 .
```

Run the application on docker:
```
docker run -d \
--name dockerize-expressjs \
-p 3000:3000 \
dockerize-example/expressjs:v1
```
With DEBUG:
```
docker run -d \
--name dockerize-expressjs \
-p 3000:3000 \
-e DEBUG=expressjs:* \
dockerize-example/expressjs:v1
```

### Docker compose
