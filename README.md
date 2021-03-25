## Workshop :: [NodeJS](https://nodejs.org/en/) and [PostgreSQL](https://www.postgresql.org/)

Configuraions
```
// Configurations
$export DB_SCHEMA=postgres
$export DB_USER=postgres
$export DB_PASSWORD=
$export DB_HOST=localhost
$export DB_PORT=5432
$export DB_SSL=false
$export PORT=3000

```

Step 1 :: Install dependencies
```
$npm install
```

Step 2 :: Test database connection
```
$npm run ping
```

Step 3 :: Testing
```
$npm run test
```

Step 4 :: Migrate data
```
$npm run migrate
```

Step 5 :: Start server
```
$npm start
```

Open url=http://localhost:3000/all in web browser

Step 6 :: API testing
* [Postman](https://www.postman.com/)
* [Newman](https://www.npmjs.com/package/newman)

```
$newman run postman/docker.postman_collection.json
```


[Next :: Working with Docker](https://github.com/up1/workshop-nodejs-postgresql/blob/main/docker-workshop.md)
