# Using NodeJS to run the server

You should have NodeJS 6.9 or greater to run this project.

Navigate to the `server` directory, and run the following to install dependencies and start the server.

```bash
npm install
node index
```

You should see boxes in the terminal of tweets as they arrive, as well as new entries appear in the Firebase database.

You **must** keep this terminal running this command as long as you wish the server to continue pushing new data into the database.

To stop the server, use `CTRL+C` to interrupt the command and stop the server.