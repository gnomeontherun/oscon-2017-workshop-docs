# Using Docker for the Angular CLI

If you are unable to setup the Angular CLI directly on your machine, you can use Docker to run a container that has it installed.

Anytime you see `ng COMMAND`, you can alternatively run the command by prefixing the `ng` command with the following. Keep in mind, it will take time to download the container the first time, but subsequent times should go much faster.

### Linux/MacOS

```bash
docker run -it --rm -w /opt -v $(pwd):/opt -p 4200:4200 rwhiteside/angular-cli ng COMMAND --host 0.0.0.0
```

### Windows

```bash
docker run -it --rm -w /opt -v %CD%:/opt -p 4200:4200 rwhiteside/angular-cli ng COMMAND --host 0.0.0.0
```