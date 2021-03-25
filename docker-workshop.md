# Working with Docker

## List of Docker images
* [NodeJS](https://hub.docker.com/_/node)
* [PostgreSQL](https://hub.docker.com/_/postgres)
* [Newman](https://hub.docker.com/r/postman/newman/)

## Step to run with Docker
```
// Configurations
$export DB_SCHEMA=postgres
$export DB_USER=postgres
$export DB_PASSWORD=
$export DB_HOST=localhost
$export DB_PORT=5432
$export DB_SSL=false
$export PORT=3000

// Build images and run containers
$docker-compose up -d --build

// See all logs
$docker-compose logs --follow

// See all services in docker-compose
$docker-compose ps

node-postgresql-docker_db_1        docker-entrypoint.sh postgres    Up       0.0.0.0:5432->5432/tcp
node-postgresql-docker_migrate_1   docker-entrypoint.sh sh -c ...   Exit 0
node-postgresql-docker_web_1       docker-entrypoint.sh npm start   Up       0.0.0.0:3000->3000/tcp
```

Testing API with curl
```
$curl --location --request PUT '127.0.0.1:3000/person' \
--header 'Content-Type: application/json' \
--data-raw '{
    "firstName": "demo",
    "lastName": "demo"
}'
```

Testing API with newman
```
// Before run, Change 127.0.0.1 to host.docker.internal or IP of Host

$docker container run --rm -v $(pwd)/postman/:/etc/newman -t postman/newman:alpine docker.postman_collection.json
```


