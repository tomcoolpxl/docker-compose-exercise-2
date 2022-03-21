## back-end

A [node.js](https://nodejs.org/en/) [REST](https://en.wikipedia.org/wiki/Representational_state_transfer) api based on [mongoose](https://mongoosejs.com/), which requires a [mongodb](https://www.mongodb.com/) instance.
The application will search for a mongodb server with the host address 'mongo' and access it on port 27017.

## front-end

A react-based UI will look for the backend api on http://localhost:8080. The UI will be served to the user on port 80 by [ngnix](https://www.nginx.com/).

## Exercise

Make sure that:

- the solution is running in docker compose and the UI is accessible on http://localhost:8880.
- the startup sequence is correct:
  1. mongodb server
  2. backend server
  3. frontend server
- the mongodb data is stored on a volume nasmed 'data'.

### Platinum level

The backend service starts only when the mongodb database **service** is up and running.

Tip: [docker compose healthcheck](https://github.com/compose-spec/compose-spec/blob/master/spec.md#healthcheck)
