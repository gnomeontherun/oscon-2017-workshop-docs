# Creating the term service

We'll need an Angular service to help us manage the server requests for changing the term. We can generate services using the CLI just like we do with components. Run the following to create a new service.

```bash
ng generate service services/term
```

This will generate two new files, a service and its corresponding test file, inside of the `src/app/services` directory.

## Add the token to localstorage

We need to add our private API token to localstorage so we can keep it private from the actual codebase.

Open up the developer tools in Chrome and navigate to the Applications tab. Here you can find the list of LocalStorage entries, expand it, and then select the store for `http://localhost:4200`.

Add a new entry by clicking on the left column and give it the name of `key` and then tab over to the value field and paste in the `API_KEY` from your `server/.env` file.

![Set key in localstorage](term-service-localstorage.png)

## Make the service

Now that we have the token in localstorage and the service files generated, we can add in the logic for the service. It will use the Http service in Angular to help build requests.

Open up `src/app/services/term.service.ts` and replace its contents with the following.

```typescript
import { Injectable } from '@angular/core';
import { Http, Headers } from '@angular/http';
import { environment } from '../../environments/environment';

@Injectable()
export class TermService {

  constructor(private http: Http) { }

  getTerm() {
    return this.http.get(environment.api + '/term');
  }

  setTerm(term) {
    let auth = new Headers();
    auth.append('Authorization', 'token ' + localStorage.getItem('key'));
    return this.http.post(environment.api + '/term', { term: term }, { headers: auth});
  }
}
```

This will help us to get or set the term value by calling the API, and also for the set request it will add the proper Authorization headers to validate the request.

We also need to add a value to our `environment` value which contains the API endpoint. Open up `src/environments/environment.ts` and update it to have the new API endpoint and point to your server, which should be `localhost:5000`.

```typescript
export const environment = {
  production: false,
  config: {
    apiKey: "AIzaSyDcwSD78uqn1jIuvsCZZdmIKDLj5qvm-ZQ",
    authDomain: "oscon-2017-workshop.firebaseapp.com",
    databaseURL: "https://oscon-2017-workshop.firebaseio.com",
    projectId: "oscon-2017-workshop",
    storageBucket: "oscon-2017-workshop.appspot.com",
    messagingSenderId: "939560207287"
  },
  api: 'http://localhost:5000'
};
```