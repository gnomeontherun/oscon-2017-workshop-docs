# Before the workshop

While you are waiting for the workshop to start, I recommend that you take care of the following steps to help speed up the workshop later. If you have trouble or are unable to get one of the following things working, there are some workarounds available where noted.

### Clone the workshop repository

Grab the source code for the project so its on your machine. It is found at https://github.com/gnomeontherun/ionic-definitive-guide.

```
git clone https://github.com/gnomeontherun/oscon-2017-workshop.git
```

If you don't have Git installed, you can download the code at https://github.com/gnomeontherun/oscon-2017-workshop/archive/master.zip

### Check NodeJS version

It is expected that your Node installation is version 6.9 or newer. Please verify your installation, and if it is older try to install the latest LTS version from https://nodejs.org.

```
node -v
```

If you are unable to get Node running on your machine, you can use Docker instead. Using [Docker for the server](server/run-with-docker.md) and [Docker for the app](setup-app)/using-docker.md).

### Check if Angular CLI is installed

We use the Angular CLI for many things, and we need to make sure you have the correct version installed.

```
ng version
```

It should output the CLI version is at least 1.0.0. If it is not, you can install it by running the following.

```
npm install -g @angular/cli@1.0.2
```

### Run NPM install on directories

Once you have the project cloned, go ahead and get the dependencies setup and installed for running the server and frontend application.

```
cd server
npm install
cd ../
ng new oscon
```