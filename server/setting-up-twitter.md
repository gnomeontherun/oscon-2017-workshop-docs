# Setting up Twitter

We need to create a Twitter application in order to access the Twitter API. This guide walks through the steps to setup your account and what parameters to use.

You'll need to login to your Twitter account and go to https://apps.twitter.com/app/new.

* Name: _Give it a meaningful name like OSCON Example_
* Description: _Give it a meaningful description like OSCON Example streaming app_
* Website: _Put in a dummy URL or your personal site_
* Callback URL: _Leave it blank_
* Developer Agreement: Yes

Once you create the app, go to the **Keys and Access Tokens** tab. Click on the button to create a Access Token near the bottom. Then you need to copy the following values into the `server/.env` file.

```
TWITTER_API_KEY=Client Key
TWITTER_API_SECRET= Client Secret
TWITTER_ACCESS_TOKEN=Access Token Key
TWITTER_ACCESS_TOKEN_SECRET=Access Token Secret
```

For good measure, also go to the **Permissions** tab and change the Access to `Read only`. We have no need for write permissions.