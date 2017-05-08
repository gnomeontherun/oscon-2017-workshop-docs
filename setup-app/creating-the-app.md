# Setting Up the App

If you want to create the app from scratch, here are the following steps to take.

## Generate a new Angular app

Start by creating a new Angular app using the Angular CLI.

```bash
ng new oscon
```

This will create a new folder with a blank Angular application ready to use. We'll need to add some additional packages to our application to use our UI library, [Clarity](https://vmware.github.io/clarity), [AngularFire2](https://github.com/angular/angularfire2), [D3](https://d3js.org) and [NgxCharts](https://github.com/swimlane/ngx-charts).

```bash
npm install --save @angular/animations clarity-angular@0.9.2 clarity-ui@0.9.2 clarity-icons@0.9.2 @webcomponents/custom-elements@1.0.0-alpha.3 mutationobserver-shim@0.3.2 firebase@3.9.0 angularfire2@4.0.0-rc.0 @swimlane/ngx-charts@5.1.2 d3@4.8.0
```

Because dependencies change and life can be hard at times, we've specified exact versions so the project should work as expected (excluding @angular/animations). There may be some warnings about version mismatches, but you can ignore them.

Now, run `ng serve` and the Angular CLI will build the project and start a local server. Go to http://localhost:4200 and you should see the message 'app works!'.