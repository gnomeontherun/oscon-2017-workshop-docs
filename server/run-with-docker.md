# Using Docker to run the server

If you have Docker installed on your system, this is the easiest way to setup and run the app.

You need to know what the path is to the project's `server` directory and map it like you see here.

```bash
docker run -p 5000:5000 -v path/to/server:/usr/src/server oscon
```

You should see boxes in the terminal of tweets as they arrive, as well as new entries appear in the Firebase database.

You **must** keep this terminal running this command as long as you wish the server to continue pushing new data into the database.

To stop the server, use `CTRL+C` to interrupt the command and stop the server.