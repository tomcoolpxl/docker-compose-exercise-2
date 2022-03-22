# Docker Compose exercise 2

This is a Docker compose exercise made for the PXL Docker Compose course.

## Project structure

## backend

A [node.js](https://nodejs.org/en/) [REST](https://en.wikipedia.org/wiki/Representational_state_transfer) api based on [mongoose](https://mongoosejs.com/), which requires a [mongodb](https://www.mongodb.com/) instance.

### backend environment variables

```
MONGO_URL=mongodb://db:27017/mongo-test
```

The api server will search for a mongodb server with the host address 'db' and access it on port 27017.

The name of the api database is mongo-test and should not be changed.

```
APP_PORT=80
```

The REST api will be served on port 80.

## frontend

A react-based UI will look for the _backend_ api on http://localhost:8080. The UI itself will be served to the user on port 80 by [ngnix](https://www.nginx.com/).

## Exercise

Create a Docker compose file and make sure that:

- the application is running on docker compose and the UI is accessible through http://localhost:8880.
- the startup sequence is as follows:
  1. mongodb server
  2. backend server
  3. frontend server
- the mongodb data is stored on a docker volume named 'data'.
- environment variables are read from a file.
- two separate networks exists so the frontend server cannot reach the database server directly.

### Platinum level

The backend service starts only when the mongodb database **service** is up and running.

Tip: [docker compose healthcheck](https://github.com/compose-spec/compose-spec/blob/master/spec.md#healthcheck)
