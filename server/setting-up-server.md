# Setting up the server

This guide will walk you through how to setup and run the server. While it is recommended to do this, you can also use the [provided server](./using-provided-server.md) if you run into issues.

The server is responsible for connecting to the Twitter stream, aggregating metrics, and pushing data to Firebase in realtime.

You can choose to run the application using NodeJS, Docker, or as an executable.

To run the application, you'll need a couple accounts.

1. Twitter account
2. Firebase account (which is a Google account)

## Setup project

All of the necessary code to run the server lives inside of the `server` directory. However, you have to ensure you have Twitter and Firebase configuration information to run the application, which we'll cover in a moment.

Copy the file `server/env.default` to `server/.env`. We'll fill in the missing values shortly.