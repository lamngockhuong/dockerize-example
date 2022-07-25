## I. On-premises
+ The App use MySQL, so we need to prepare MySQL server and update database connection information at `app.py` file
```
mydb = mysql.connector.connect(
  host="locahost",
  user="root",
  password="p@ssw0rd1",
  database="inventory"
)
```
+ Install requirements:
```
$ pip3 install -r requirements.txt
```

+ Run the app with this command:
```
$ python3 -m flask run
```

To test that the application is working properly, access to http://localhost:5000

## II. Docker - Docker compose
### Docker
+ Run MySQL Server:
```
$ docker volume create mysql
$ docker volume create mysql_config
$ docker network create mysqlnet
$ docker run --rm -d -v mysql:/var/lib/mysql \
  -v mysql_config:/etc/mysql -p 13306:3306 \
  --network mysqlnet \
  --name mysqldb \
  -e MYSQL_ROOT_PASSWORD=p@ssw0rd1 \
  mysql
```

+ Build flask hello-world image
```
$ cd python/hello-world/
$ docker build -t dockerize-example/flask-hello-world:v1 .
```

+ Add the container to the database network and then run our container (This allows us to access the database by its container name):
```
$ cd python/hello-world/
$ docker run --rm -d \
--name dockerize-flask-hello-world \
--network mysqlnet \
-p 5000:5000 \
dockerize-example/flask-hello-world:v1
```

### Docker compose
+ Run the application:
```
$ cd python/hello-world/
$ docker compose -f docker-compose.dev.yml up --build
```

+ Stop:
```
$ cd python/hello-world/
$ docker compose -f docker-compose.dev.yml stop
```
