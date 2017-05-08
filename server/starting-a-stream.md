# Starting a stream

When you run your own server, you will need to provide a term to the server that will start running a Twitter stream against that term.

## API Authentication

The API has a basic authentication requirement, which is to pass the `Authorization` header with a token. In the `server/.env` file, you will need to put in a unique string before running your server.

```
API_KEY=YOUR_CUSTOM_TOKEN
```

## Start a stream on a term

To start a stream, you'll make a POST request to the following API in order to start a new stream on a given term. This is the API call to make, a POST with a body with a JSON object.

```
POST http://localhost:5000/term {"term":"javascript"}
```

You can call the API using cURL like you see here.

```bash
 curl -X POST \
  http://localhost:5000/term \
  -H 'authorization: token YOUR_CUSTOM_TOKEN' \
  -H 'content-type: application/json' \
  -d '{
        "term": "javascript"
}'
```

## Get the current stream term

You can request the current term by making the following request. This does not require authentication to request.

```
GET http://localhost:5000/term
```