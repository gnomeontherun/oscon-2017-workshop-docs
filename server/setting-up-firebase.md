## Configure for Firebase

This application uses Firebase as a database, because it has some unique properties that help manage

Go to https://console.firebase.google.com and login to your Google account. Firebase is free to use for our use cases.

Create a new project from the console, giving it any name you find meaningful. Once it has been created, open it and click on the **cog icon** next to the **Overview** link in the sidebar. Select **Project settings** and then **Service accounts**.

Generate a new private key using the button near the bottom, which will download a JSON file onto your computer. You'll need to copy that file into the project into the `server` directory, and call the file `firebase.config.json`.

Then click on the **Database** url in the sidebar, and there is a URL in the following format `https://[PROJECT_ID].firebaseio.com/`. Copy this value, and update the `FIREBASE_DATABASE` property in the `server/.env` file with this value.

```
FIREBASE_DATABASE=https://PROJECT_ID.firebaseio.com/
```

Now click on the **Rules** tab of the Database section, and copy the following into the text area and select Publish. This will allow read access to the database without requiring authentication, and also index the list by created time.

```json
{
  "rules": {
    ".read": true,
    ".write": "auth != null",
    "hashtags": {
      ".indexOn": "count"
    },
    "links": {
      ".indexOn": "count"
    },
    "tweets": {
      ".indexOn": "timestamp_ms"
    }
  }
}
```